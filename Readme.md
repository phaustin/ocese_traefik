# OCESE traefik configuration

The pemfile branch sets traefik up to use UBC certfiles stored in traefik/config/certs.
Traefik's file provider will watch the config folder and refresh the certificates if
the yml files config/dynamic are touched.

See this discussion:  https://community.traefik.io/t/how-to-renew-update-user-defined-custom-certificates/20598/6

You can also restart traefik from ~/repos/ocese_traefik by doing:

      docker compose down
      docker compose up -d
      

# installation notes

## local installation on macos

https://medium.com/nerd-for-tech/how-to-use-traefik-on-localhost-2b566825f94f

### generate certificates

openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout localhost.key -out localhost.crt

https://stackoverflow.com/questions/10175812/how-can-i-generate-a-self-signed-ssl-certificate-using-openssl

# Interactive
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 365

# Non-interactive and 10 years expiration
openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -sha256 -days 3650 -nodes -subj "/C=XX/ST=StateName/L=CityName/O=CompanyName/OU=CompanySectionName/CN=CommonNameOrHostname"

https://betterstack.com/community/questions/getting-chrome-to-accept-self-signed-localhost-certificate/



