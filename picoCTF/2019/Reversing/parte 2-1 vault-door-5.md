In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)

Hints:
1. You may find an encoder/decoder tool helpful, such as https://encoding.tools/
2. Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.

## Solución

Analizando el código, vemos que el password primero se convierte en un array de bytes, después se convierte en hexadecimal y al final se encripta por base64.
El password ya esta en el código en el método **checkPassword** llamado en la variable **expected**. Teniendolo ahí, podemos hacer la invers del proceso.

Creamos , métodos: urldecode y base64Decode. Dónde primero convertimos a base64 decodificandolo y obteniendo el hexadecimal, después lo pasamos de hexadecimal a bytes, obteniendo eso podemos convertir los bytes en un string y obtenemos el password.
``` java
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
	String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
	if (vaultDoor.checkPassword(input)) {
	    System.out.println("Access granted.");
	} else {
	    System.out.println("Access denied!");
        }
    }

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    public byte[] base64Decode(String input) {
        return Base64.getDecoder().decode(input);
    }

	public byte[] urldecode(String input){

		input = input.replace("%","");
		
		byte[] ans = new byte[input.length() / 2];

		for(int i = 0 ; i < ans.length ; i++){
			int index = i*2;

			int val = Integer.parseInt(input.substring(index, index + 2), 16);
			ans[i] = (byte)val;
		}

		return ans;
	}


    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1";

	String decode = new String( base64Decode(expected) );
	String urldecode = new String( urldecode(decode) );

	System.out.println(decode);
	System.out.println(urldecode);


        return base64Encoded.equals(expected);
    }
}

```

El primer intento solo es de prueba para obtener el password.
``` bash
holiwiscach@ubuntu:~/vault5$ java VaultDoor5
Enter vault password: picoCTF{ola}
%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%38%34%66%64%35%30%39%35
c0nv3rt1ng_fr0m_ba5e_64_84fd5095
Access denied!

```

El segundo intento ya ingresamos el password correcto y entramos.
``` bash
holiwiscach@ubuntu:~/vault5$ java VaultDoor5
Enter vault password: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}
%63%30%6e%76%33%72%74%31%6e%67%5f%66%72%30%6d%5f%62%61%35%65%5f%36%34%5f%38%34%66%64%35%30%39%35
c0nv3rt1ng_fr0m_ba5e_64_84fd5095
Access granted.

```

bandera:
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}
