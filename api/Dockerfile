FROM haskell:8

RUN export PATH=$(stack path --local-bin):$PATH

RUN mkdir -p /app/user
WORKDIR /app/user
COPY stack.yaml .
COPY *.cabal ./
RUN stack build --dependencies-only

COPY . /app/user
RUN stack install
