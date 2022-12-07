# spring_boot_3_with_vault

Run Vault in a container, it will start in dev mode already:
```
sudo docker run --cap-add=IPC_LOCK -e 'VAULT_DEV_ROOT_TOKEN_ID=myroot' -e 'VAULT_DEV_LISTEN_ADDRESS=0.0.0.0:8200' -p 8200:8200 vault
```

Run the spring application.
This is the error I get:
```
java.lang.NoClassDefFoundError: org/apache/hc/client5/http/classic/HttpClient
	at org.springframework.vault.client.ClientHttpRequestFactoryFactory$HttpComponents.usingHttpComponents(ClientHttpRequestFactoryFactory.java:333)
```

If you downgrade to Spring Boot 2.7.6 the application starts.
