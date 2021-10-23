# How to create new private key file, cert file, and public key file

1. Create new private key.
    ```
    $ keytool -genkeypair -alias <shortName> -keyalg RSA -dname "CN=<commonName>, OU=<organizationUnit>, O=<organizationName>, L=<localityName>, C=<country>" -keypass "<password>" -keystore <privateKeyfileName> -storepass "<password>"
    ```

2. Get cert file by using the private key file.
    ```
    $ keytool -export -alias <shortName> -keystore <privateKeyFileName> -rfc -file <newCertFileName>.cert
    ```

3. Get public key file by using the cert file.
    ```
    $ keytool -import -alias <shortName> -file <certFileName> -keystore <newPublicKeyFileName>.jks
    ```

