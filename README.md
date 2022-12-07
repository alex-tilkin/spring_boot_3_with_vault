# spring_boot_3_with_vault

Install Vault on your machine and run in dev mode:

```
brew tap hashicorp/tap
brew install hashicorp/tap/vault
vault server -dev
```

or run in a container, it will start in dev mode already:
```
sudo docker run --cap-add=IPC_LOCK -e 'VAULT_DEV_ROOT_TOKEN_ID=myroot' -e 'VAULT_DEV_LISTEN_ADDRESS=0.0.0.0:8200' -p 8200:8200 vault
```

Pick the Root Token value and set it as environment variable so Spring can pick it up.

It will look like this:
Root Token: myroot

```
export VAULT_ADDR='http://0.0.0.0:8200'
export VAULT_ROOT_TOKEN=myroot
```

Run the spring application.
This is the error I get:
```
java.lang.NoClassDefFoundError: org/apache/hc/client5/http/classic/HttpClient
	at org.springframework.vault.client.ClientHttpRequestFactoryFactory$HttpComponents.usingHttpComponents(ClientHttpRequestFactoryFactory.java:333)
```
