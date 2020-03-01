<h1 align="center">
    <a href="https://github.com/Shpota/goxygen/tree/master/.github/README.md">
        <img height="25px" src="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.4.6/flags/4x3/gb.svg">
    </a>
    <a href="https://github.com/Shpota/goxygen/tree/master/.github/README_ua.md">
        <img height="20px" src="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.4.6/flags/4x3/ua.svg">
    </a>
    <a href="https://github.com/Shpota/goxygen/tree/master/.github/README_ru.md">
        <img height="20px" src="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.4.6/flags/4x3/ru.svg">
    </a>
    <a href="https://github.com/Shpota/goxygen/tree/master/.github/README_zh.md">
        <img height="20px" src="https://cdnjs.cloudflare.com/ajax/libs/flag-icon-css/3.4.6/flags/4x3/cn.svg">
    </a>
    <br>
    Goxygen
    <a href="https://github.com/Shpota/goxygen/actions?query=workflow%3Abuild">
        <img src="https://github.com/Shpota/goxygen/workflows/build/badge.svg">
    </a>
    <a href="https://github.com/Shpota/goxygen/releases">
        <img src="https://img.shields.io/badge/version-v0.1.0-green">
    </a>
    <a href="https://gitter.im/goxygen/community">
        <img src="https://badges.gitter.im/goxygen/community.svg">
    </a>
    <a href="https://github.com/Shpota/goxygen/pulls">
        <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square">
    </a>
</h1>

<img src="../templates/react.webapp/src/logo.svg" align="right" width="230px" alt="goxygen logo">

**Genera in pochi secondi un progetto web Full Stack con Go, React, e MongoDB.**

L' obiettivo di Goxygen e' quello di far risparmiare tempo nella crezione 
di un nuovo progetto. Crea lo scheletro dell'appplicazione, configurazioni 
comprese. 
Goxygen genera il codice di backend scritto in Go, lo connette con il
frontend scritto in React, fornisce il Dockerfile e il docker-compose 
utili per ambienti di sviluppo e produzione.


## Come i usa

Hai bisogno di Go 1.11 o superiore.
```go
go get -u github.com/shpota/goxygen
go run github.com/shpota/goxygen init my-app
```
Il secondo comando genera nella cartella `my-app` il nuovo  progetto.

Il progetto e' gia' pronto per essere eseguito con il comando `docker-compose`:
```sh
cd my-app
docker-compose up
```
L'applicazione è accessibile all'indirizzo
http://localhost:8080.

Puoi trovare ulteriori dettagli suil codice generato in questo file.

![Showcase](showcase.gif)

## Struttura del progetto

    my-app
    ├── server                   # Go file
    │   ├── db                   # MongoDB
    │   ├── model                # domain objects
    │   ├── web                  # REST APIs, web server
    │   ├── server.go            # server backend
    │   └── go.mod               # dipendenze Go
    ├── webapp                    
    │   ├── public               # icone, file statici  e index.html
    │   ├── src                       
    │   │   ├── App.js           # Componente principale in React
    │   │   ├── App.css          # file con i css dell'applicazione
    │   │   ├── index.js         # the entry point dell'applicazione          
    │   │   └── index.css        # css globali
    │   ├── package.json         # dipendenze della parte front end
    │   ├── .env.development     # API endpoint per l'ambiente di sviluppo
    │   └── .env.production      # API endpoint per l'ambiente di produzione
    ├── Dockerfile               # builds back end and front end together
    ├── docker-compose.yml       # docker-compose per per il deployment nell'ambiente di produzione
    ├── docker-compose-dev.yml   # docker-compose per l'ambiente di sviluppo, fa partire un server MongoDB locale
    ├── init-db.js               # crea una collezione con dati di test su MongoDB
    ├── .dockerignore            # specifica i file ignorati nel build con Docker
    ├── .gitignore
    └── README.md                # guisa su come usare il codice generato


Unit test o componenti di esempio non sono inclusi.

## Dependenze

Goxygen generates a basic structure of a project and doesn't force you
to use a specific set of tools. That's why it doesn't bring unneeded
dependencies to your project. The only two dependencies are
[mongo-go-driver](https://github.com/mongodb/mongo-go-driver) on the
back end side and [axios](https://github.com/axios/axios) on the front
end side.

## How to contribute

If you found a bug or have an idea on how to improve the project
[open an issue](https://github.com/Shpota/goxygen/issues)
and we will fix it as soon as possible.

You can also propose your changes via a Pull Request. Fork the
repository, make changes, send us a pull request and we'll
review it shortly.

### Credits
Goxygen's logo was created by [Egon Elbre](https://twitter.com/egonelbre).
