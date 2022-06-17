VERSION 0.6

FROM earthly/dind:ubuntu

RUN apt-get update -yq \
        && apt-get -yq install curl gnupg ca-certificates gcc g++ make \
        && curl -L https://deb.nodesource.com/setup_16.x | bash \
        && apt-get update -yq \
        && apt-get install -yq nodejs

WORKDIR /workspace

this-works:
    WITH DOCKER --pull hello-world
        RUN docker run hello-world
    END

this-does-not:
    COPY --dir ./* ./
    RUN npm i
    WITH DOCKER
        RUN npm test
    END
