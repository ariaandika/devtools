# Dev Tools

Personal documentation of what i learned

some of it has a link to more detailed explanation, while other i havent been deep dive into it

content:

- [Programming Language](#programming-language)
- [Server](#server)
- [Database](#database)
- [Web](#web)
- [Full Stack](#fullstack)
- [Linux](#linux)
- [Web Api](#web-api)
- [Design Pattern](#design-pattern)
- [Data](#data)
- [Dev Tools](#dev-tools)
- [Graphical User Interface](#graphical-user-interface)
- [Game](#game)
- [Monorepo](#monorepo)
- [Other](#other)

## Programming Language

- Rust  
  used to make performance critical app  
  memory safe by using borrow checker instead of garbage collection  
  really good at error handling  

- C#  
  full object oriented language features  
  well established framework for building cross platform app  
  used for building game with Unity  

- Go  
  lot of built in tools for web development  
  high performance  
  simplicity  

- [Bash](./linux/bash.md)  
  a scripting language for interacting with operating system  

- Javascript  
  easy to learn  
  used for client side app / browser  
  popular choice for server side app

- Typescript  
  add type system on top of javascript  

- Python  
  easy to learn  
  have a lot of library involving in data science  
  popular choice for machine learning  

- Lua  
  high performance for interpreted language  
  well suit for embedded language  

- PHP  
  language for building server side app  
  lot of built in feature for server side app  

- C  
  a high performance low level language  
  manual memory management  

- sql  
  a query language for relational database  

- wasm  
  high performance  
  suits for embeded system  
  its build from other language, so no need to learn new language  

- cmd  
  interpreted language for interacting with windows os  

- Kotlin  
  language for building mobile app as alternative to java  

- Dart  
  language for building cross platform app with flutter framework  

- C++  
  superset of c with object oriented language  

- ruby  
  object oriented, dynamic type language  
  popular choice for server side application with ruby on rails framework

interested but havent deep dive yet:

- zig, nim, mojo

other

- elixir, perl, ocaml, carbon

## Server

Web Server App

- Bun  
  high performance  
  built in convinient api  
  can run typescript  
  all in one tools (package manager, testing, bundler)  

- Go  
  lot of built in features for making high performance server app
  
- NodeJS  
  is a popular javascript runtime with so many framework to choose from

- Rust
  rust have a low level module for interacting with os Tcp/ip  
  there is a wide range of framework to choose from that achive high performance server app
  
- Deno  
  a alternative for nodejs with a lot of feature built in where nodejs need to install extra tools

- nginx  
  ready to use web server  
  can be used for reverse proxy

- Apache  
  same purpose with nginx  

Protocol

- Hypertext Transfer Protocol
  - RestApi
  - GraphQL
- Websocket
- Remote Procedural Call
  - tRPC
  - gRPC
- RTC
- File Transfer Protocol
- Language Server Protocol
- RabbitMQ

Api Service

- OAuth
- Stripe

[Domain name resolver](./server/dns.md)

[Email Server](./server/mail.md)

## Linux

Distro

- Arch
- Debian
- Fedora
- openSuse
- Gentoo

Commands

- to many to list

Shell

- [bash](./linux/bash.md)
- zsh
- fish

Programs

- tmux
- [fzf](./linux/fzf.md)
- neovim

Display Server

- xorg

Window Manager

- i3

## Dev Ops

Version Control

- git
- github

Deployment

- Docker
- Kubernetes
- Terraform

## Database

Model

- Relational
- Document
- Key Value
- Wide Column
- Graph

Database Management System

- MySQL
- Postgres
- Redis
- SQLite
- SurealDB
- Neo4j
- meilisearch

Service

- Pocketbase
- Supabase
- Firebase
- MongoDB

Object Relational Mapper

- Drizzle
- Prisma
- Diesel
- Eloquent
- Gorm
- Entity Core

## Web

[Web](./client/readme.md) is the easiest platform to get started with app development.

[Javascript](./client/readme.md#javascript)

- [React](./client/react.md), javascript frontend library
- [Svelte](./client/svelte.md), javascript frontend library

[CSS](./client/readme.md#css)

- Tailwindcss, building block css library
- Bootstrap, ready to use css component library
- Sass, css with programmatic feature
- Postcss, auto add css boring boilerplate

HTML

- ejs, html template using embedded js
- blade, different take on php
- php, the og hypertext preprocessor

## Fullstack

- NextJS, full featured metaframework that uses react as frontend
- SvelteKit, svelte's official backend framework that can be deployed anywhere
- Laravel, php framework for web artisans
- Qwik
- Astro
- HUGO

## Web Api

- JSON Web Token
- Cookie Session
- Cors
- Web Worker

## Design Pattern

[Software Design Pattern](./design/design-pattern.md) is a pattern that we can follow to achieve consistency and predictable code.

Builder Pattern

- Factory
- Builder
- Singleton
- Prototype

Behavioral Pattern

- Observer
- Iterator
- Strategy

## Data

Data structure

- list
- array
- stacks
- queue
- heap
- tree
  - b tree
  - b+ tree
- hash table
- suffix tree
- graph
- R tree

## Dev tools

Editor

- vscode
- neovim
- rider

Web Build Tools

- Vite
- Webpack
- Rollup
- esbuild
- Turbopack

Testing

- postman
- insomnia
- cypress
- vitest
- jest

Machine Learning

- libraries
  - Tensorflow
  - PyTorch
  - NumPy
  - Pandas

Machine learning technique

- deep learning
- reinforcement learning

Machine learning model

- neural network
- deep neural network
- convolutional neural network
- recurrent neural network

Algorithm

- sorting algorithm
  - quicksort
- search algorithm
  - linear
  - binary
- decision algorithm
  - alpha beta pruning

## Graphical User Interface

Desktop

- Rust
  - egui
- Tauri
- Electron

Mobile App

- Android Studio
- Flutter
- React Native

## Game

Game Engine

- Unity
- Game Maker Studio
- Godot
- Unreal Engine

Game Theory

- path finding

## Monorepo

- Turborepo
- Nx

## Other

- cryptography
- logic gate
- shader

