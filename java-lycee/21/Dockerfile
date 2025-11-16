FROM --platform=$TARGETOS/$TARGETARCH eclipse-temurin:21-jre

LABEL author="Funasitien" maintainer="hello@funa.dev"

LABEL org.opencontainers.image.source="https://github.com/Funasitien/DockerImages"
LABEL org.opencontainers.image.licenses=MIT

# Chemin du vrai keystore Java
ENV CACERTS_PATH=/usr/lib64/graalvm/graalvm-java25/lib/security/cacerts

# Copier ton certificat
COPY lycee.crt /tmp/lycee.crt

# Importer le certificat dans cacerts
RUN keytool -importcert \
    -noprompt \
    -trustcacerts \
    -alias lycee \
    -file /tmp/lycee.crt \
    -keystore $CACERTS_PATH \
    -storepass changeit
