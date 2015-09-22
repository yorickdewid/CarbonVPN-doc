# Quick start
Assuming you have installed or compiled CarbonVPN successfully.

## 1. Setup Server
First you must generate the ca information.
Assuming you are in the correct folder, run CarbonVPN.
```
./carbond genca
```
This will output the cacert, public key and private key to screen.
You will need to copy these into the __vpn.conf__ file.
Replace the following entries:
```
cacert = <YOUR CACERT>  ; CA certificate
capublickey = <YOUR CAPUBLIC KEY>  ; CA public key
caprivatekey = <YOUR CAPRIVATE KEY> ; CA private key, only on server
```
Next generate the certificates:
```
./carbond gencert
```
And replace the following entries in __vpn.conf__:

```
publickey = <YOUR PUBLIC KEY>       ; Public key
privatekey = <YOUR PRIVATE KEY>     ; Private key
```

## 2. Setup client
### note:
Make sure router option is left disabled in client config.

Open and edit vpn.conf file and add the public key/private key from the server:
```
publickey = <YOUR PUBLIC KEY>; Public key
privatekey = [YOUR PRIVATE KEY]; Private key
```
###note:
Filling in the private key is optional since it can be calculated by the client.

## 3. Connecting


Assuming you are in the correct folder, and root:
```
./carbond -f vpn.conf -c [X.X.X.X]
```
check if interface was added:
```
ifconfig
```

execute a ping to server ip as a test:

```
ping [x.x.x.x]
```