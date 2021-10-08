FROM earthly/dind:ubuntu

this-works:
    WITH DOCKER --pull hello-world
        RUN docker run hello-world
    END

this-does-not:
    COPY ./ ./
    RUN apt-get update -yq \
        && apt-get -yq install curl gnupg ca-certificates gcc g++ make \
        && curl -L https://deb.nodesource.com/setup_16.x | bash \
        && apt-get update -yq \
        && apt-get install -yq nodejs
    RUN npm i
    WITH DOCKER
        RUN npm test
    END