<!DOCTYPE html>
<html>
<head>
  <title>ML Lab Website</title>
  <style>
    body {
      font-family: sans-serif;
      background: #f9f9f9;
      margin: 0;
    }
    nav {
      background: #333;
      color: white;
      display: flex;
      padding: 10px;
      flex-wrap: wrap;
    }
    nav a {
      color: white;
      margin-right: 20px;
      text-decoration: none;
      font-weight: bold;
      cursor: pointer;
    }
    .content {
      display: none;
      padding: 20px;
    }
    .active {
      display: block;
    }
    pre {
      background: #fff;
      padding: 15px;
      border-radius: 5px;
      overflow-x: auto;
      font-family: monospace;
    }
    iframe {
      width: 100%;
      height: 600px;
      border: none;
    }
  </style>
</head>
<body>
  <nav>
    <a onclick="showTab('exp3')">EXP-3</a>
    <a onclick="showTab('mlLab')">ML-LAB</a>
    <a onclick="showTab('exp8a')">8a</a>
    <a onclick="showTab('exp8b')">8b</a>
  </nav>

  <div id="exp3" class="content active">
    <h2>Experiment 3 - Decision Tree</h2>
    <pre>...Your Experiment 3 Python code...</pre>
  </div>

  <div id="mlLab" class="content">
    <h2>ML-LAB PDF</h2>
    <iframe src="https://drive.google.com/file/d/1rxTNSsfOiMvcMDNFcS1K_IQla86DyiJD/preview" allow="autoplay"></iframe>
  </div>

  <div id="exp8a" class="content">
    <h2>Experiment 8a - RSA Algorithm (Java)</h2>
    <pre>
import java.math.BigInteger;
import java.security.SecureRandom;

public class RSA {
    public static void main(String[] args) {
        try {
            SecureRandom rand = new SecureRandom();
            BigInteger p = BigInteger.probablePrime(512, rand);
            BigInteger q = BigInteger.probablePrime(512, rand);

            BigInteger n = p.multiply(q);
            BigInteger phi = p.subtract(BigInteger.ONE).multiply(q.subtract(BigInteger.ONE));
            BigInteger e = BigInteger.valueOf(65537);
            BigInteger d = e.modInverse(phi);

            String message = "Hello, RSA!";
            BigInteger msg = new BigInteger(message.getBytes());

            BigInteger cipher = msg.modPow(e, n);
            BigInteger decrypt = cipher.modPow(d, n);
            String dec = new String(decrypt.toByteArray());

            System.out.println("Encrypted: " + cipher);
            System.out.println("Decrypted: " + dec);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
    </pre>
  </div>

  <div id="exp8b" class="content">
    <h2>Experiment 8b - Bitwise AND/XOR in C</h2>
    <pre>
#include &lt;stdio.h&gt;
int main()
{
    char *str = "Hello World";
    printf("Original string:%s\n", str);
    printf("After AND operation with 127:\n");
    for (int i = 0; str[i] != '\0'; i++)
    {
        char and_result = str[i] & 127;
        printf("%c", and_result);
    }

    printf("\n");
    printf("After XOR operation with 127:\n");
    for (int i = 0; str[i] != '\0'; i++)
    {
        char xor_result = str[i] ^ 127;
        printf("%c", xor_result);
    }

    printf("\n");
    return 0;
}
    </pre>
  </div>

  <script>
    function showTab(tabId) {
      document.querySelectorAll('.content').forEach(c => c.classList.remove('active'));
      document.getElementById(tabId).classList.add('active');
    }
  </script>
</body>
</html>
