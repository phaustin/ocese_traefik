# OCESE traefik configuration

The pemfile branch sets traefik up to use UBC certfiles stored in traefik/config/certs.
Traefik's file provider will watch the config folder and refresh the certificates if
the yml files config/dynamic are touched.

See this discussion:  https://community.traefik.io/t/how-to-renew-update-user-defined-custom-certificates/20598/6

