# knot-resolver
Knot resolver configuration file: config.yaml

## Commands ##

**Validate config file:**
    
    sudo kresctl validate /etc/knot-resolver/config.yaml

**Reload knot resolver:**

    sudo systemctl reload knot-resolver.service

## Configuration options for DoT and DoH ##

**Note**

These settings affect both DNS-over-TLS and DNS-over-HTTPS (including the legacy implementation).

A self-signed certificate is generated by default. For serious deployments it is strongly recommended to configure your own TLS certificates signed by a trusted CA.

network/tls:

cert-file: *path*

key-file: *path*

    network:    
      tls:      
        cert-file: /etc/knot-resolver/server-cert.pem        
        key-file: /etc/knot-resolver/server-key.pem

> **Tip**
> The certificate files aren’t automatically reloaded on change. If you update the certificate files, e.g. using ACME, you have to either reload or restart the service(s).


[^note]:
https://www.knot-resolver.cz/documentation/latest/index.html
