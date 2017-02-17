### Security

The following security measures could in place for a hosted environment:
### Cloud security
- DDOS protection
- IPSEC VPN connections
- IP whitelisting

Most cloud envionments support these features.

### Operating System 
- Hardened operating systems (according to Center of Internet Security)

### Platform security
- Communication over TLS
- Firewalls between all servers and layers
- Certificates from a certificate authority
- Audit trail on all actions throughout the platform
- Role based authorizations on specific functions of devices
- Access control
- Unique device identification

For every major release there will be a mandated security test initiated by Smart society services.

In cooperation with the European Network of Cyber Security (ENCS) state of the art security measures were implemented.

- Security per device
- Security per application 
- Security Certificates per Organisation and per device
- All communication is encrypted

 ![alt text](./functional-layers-overview.png "Functional Layers Overview")

**Security measures:**
1. Firewall in defined zone
2. Operating System Hardening
3. DDOS protection
4. Replay attack prevention
5. Private encryption key per device
6. Certificates from a Certificate Authority
7. Encryption via Elliptic Curve DSA
8. IPSEC VPN for CDMA and GPRS
9. Unique device identification
10. Unique CDMA modem number
11. Role based authorizations on functions and devices

#### Encryption

An analysis of safety aspects has led to the decision that the safety of the whole system will be realized by proven technology based on asymmetrical coding (Also known as public-key encryption).

#### Authentication of web-applications

Two way SSL will be used between web-applications and the open smart grid platform to verify the identities for both parties. User organisations are responsible for the administration of the identity of and access to their web applications. The web applications feature a login page. After successful login the user is linked to an organisation. Passwords will be stored encrypted. The organisation ID will be sent in each message to the open smart grid platform and will be verified by the SSL certificate.

#### Algorithms

Only public encryption Algorithms will be used. Due to performance limitations (of the devices) and recommendations from The European Network for Cyber Security (ENCS) Elliptic Curve DSA with 256-bit-keys was selected. This improves the security and efficiency over the 1024 bit RSA algorithm. Messages can be smaller and less processor capacity is needed. The key length of Elliptic Curve DSA is similar to the 3072 bit key length of RSA.

Note: Even though the open smart grid platform uses ECDSA to secure the OSLP, other encryptions may be used as well. The RSA Algorithm is still supported if preferred. This is a flexible configuration option.

#### Private APN

A private APN is used for linking to mobile data communication infrastructures.

 ![alt text](./private-apn.png "Private APN")



### Logging
* Every action to and from devices is logged in the audittrail
* Messages from unknown devices will be denied (and logged)
