How to add SSL certification to any application:

1.Create a keystore by entering following command.
keytool -genkey -alias mydomain -keyalg RSA -keystore keystore.jks -keysize 2048

2.Then import the .jks file into another destination file of type PKCS12 with .p12 extension.
keytool -importkeystore -srckeystore keystore.jks -destkeystore keystore.p12 -deststoretype PKCS12

3.Then use following command to create certificate out of that .p12 file.
openssl pkcs12 -in keystore.p12 -nokeys -out my_key_store.crt

4.Now add the .crt file to your browser's certificate list by going to 
chrome://settings > Advanced > Manage Certificates > Import

5. Follow this tutorial: https://www.thomasvitale.com/https-spring-boot-ssl-certificate/

To create keystore and certificate through java code, visit the following link:
http://www.baeldung.com/java-keystore
