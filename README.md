# spring_boot_3_with_vault

Install Vault on you machine and run in dev mode:

```
brew tap hashicorp/tap
brew install hashicorp/tap/vault
vault server -dev
```

or run in a container, it will start in dev mode already:
```
sudo docker run vault
```

Pick the Root Token value and set it as environment variable so Spring can pick it up.

It will look somethig like:
Root Token: hvs.SwCW6CcBVyfthduihvRjuenE

```
export VAULT_ROOT_TOKEN=hvs.SwCW6CcBVyfthduihvRjuenE
```

Run the spring application.
This is the error I get:
```
java.lang.NoClassDefFoundError: org/apache/hc/client5/http/classic/HttpClient
	at org.springframework.vault.client.ClientHttpRequestFactoryFactory$HttpComponents.usingHttpComponents(ClientHttpRequestFactoryFactory.java:333)
```
