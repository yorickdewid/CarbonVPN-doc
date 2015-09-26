# Quick start
Assuming you have installed or compiled CarbonVPN successfully.

## 1. Server setup
First you must generate the CA certificate.
Assuming you are in the correct directory, run CarbonVPN with the `genca` option.

```
./carbond genca
```

This will output the CA certificate, CA public key and CA private key.
You will need to copy these into the __vpn.conf__ file.
Replace the following entries:

```
cacert = <YOUR CACERT>
capublickey = <YOUR CAPUBLIC KEY>
caprivatekey = <YOUR CAPRIVATE KEY>
```
Save the config file before you continue. Next generate the server certificate:

```
./carbond gencert
```

And replace the following entries in __vpn.conf__:

```
publickey = <YOUR PUBLIC KEY>
privatekey = <YOUR PRIVATE KEY>
```
### Clients

For every client you will need to repeat this step. In this example we will assume there is only one client.

Generate the client certificate:

```
./carbond gencert
```

You will need both keys for the next step.

## 2. Client setup

Open the vpn.conf file on the client and add the public key/private keypair generated in the previous step:

```
publickey = <YOUR PUBLIC KEY>
privatekey = <YOUR PRIVATE KEY>
```

In addition to this client keypair you must also copy the cacert and capublickey from the server.

**Note:** the caprivatekey is *always* empty in the client configurations.

## 3. Client connect

Now on the client machine, run as root:

```
./carbond -f vpn.conf -c <VPN SERVER IP>
```

You can manually verify that the connection was established. Run `ifconfig` or `ip link show` and look for the tunnel interface. By default that would be `tun0`

Now check the connection itself. Execute a ping to server ip as a test. If you followed this guide so far you can reach the server using:

```
ping 10.7.0.1
```