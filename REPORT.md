# Informe de Ejecución del Pipeline

## Resumen

Este informe describe los pasos realizados para configurar y ejecutar el pipeline de CI/CD para el proyecto "TechFlow" API.

## Pasos

1. **Gestión del Repositorio Git**  
     
   - Se inicializó un repositorio local y se conectó a GitHub.
   - Se hizo commit de una versión inicial de los archivos solicitados

   

2. **Configuración básica de una API**  
     
   - Se verifica funcionamiento de la API
   

   

3. **Configuración de Jenkins**  
     
   - Se configuró Jenkins para automatizar el proceso de construcción, prueba y despliegue.
   - Se usó opción "Pipeline script from SCM"
   - Se usó nombre del Branch: main
   - Y para Script path: Dockerfile 


## Problemas Encontrados

- \[Sección opcional para problemas\]


## Resultados

## Ejecución del Pipeline en Jenkins

```text
Started by user Diego Gonzalez

Obtained Jenkinsfile from git https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins
 in C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua # timeout=10
Fetching upstream changes from https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua
 > git.exe --version # timeout=10
 > git --version # 'git version 2.46.0.windows.1'
 > git.exe fetch --tags --force --progress -- https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/main^{commit}" # timeout=10
Checking out Revision a04bbb7ca632c03a55eede4bfcd3446df9a01d6d (refs/remotes/origin/main)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f a04bbb7ca632c03a55eede4bfcd3446df9a01d6d # timeout=10
Commit message: "Rename jenkinsfile to Jenkinsfile"
 > git.exe rev-list --no-walk d81ff750107ac3bbfd2aee3031f36afbac1d9fc2 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Checkout)
[Pipeline] echo
📥 Clonando el repositorio...
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git.exe rev-parse --resolve-git-dir C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline\.git # timeout=10
Fetching changes from the remote Git repository
 > git.exe config remote.origin.url https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua # timeout=10
Fetching upstream changes from https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua
 > git.exe --version # timeout=10
 > git --version # 'git version 2.46.0.windows.1'
 > git.exe fetch --tags --force --progress -- https://github.com/DiegoGonzalezBaeza/Prueba_Pipeline_Integracion_Continua +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git.exe rev-parse "refs/remotes/origin/main^{commit}" # timeout=10
Checking out Revision a04bbb7ca632c03a55eede4bfcd3446df9a01d6d (refs/remotes/origin/main)
 > git.exe config core.sparsecheckout # timeout=10
 > git.exe checkout -f a04bbb7ca632c03a55eede4bfcd3446df9a01d6d # timeout=10
Commit message: "Rename jenkinsfile to Jenkinsfile"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] script
[Pipeline] {
[Pipeline] echo
⚙️ Instalando dependencias...
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline>npm install 
npm warn deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm warn deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
npm warn deprecated superagent@8.1.2: Please upgrade to v9.0.0+ as we have fixed a public vulnerability with formidable dependency. Note that v9.0.0+ requires Node.js v14.18.0+. See https://github.com/ladjs/superagent/pull/1800 for insight. This project is supported and maintained by the team at Forward Email @ https://forwardemail.net

added 355 packages, and audited 356 packages in 5s

48 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline>npm run build 

> ci_pipeline_project@1.0.0 build
> echo 'No hay proceso de compilación en este proyecto'

'No hay proceso de compilaci�n en este proyecto'
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] script
[Pipeline] {
[Pipeline] echo
🧪 Ejecutando pruebas...
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline>npm test 

> ci_pipeline_project@1.0.0 test
> jest --coverage --forceExit

  console.log
    Servidor corriendo en http://localhost:3000

      at Server.log (app.js:24:32)

PASS tests/app.test.js
  API Tests
    √ should return a list of users (62 ms)
    √ should return a single user (7 ms)

----------|---------|----------|---------|---------|-------------------
File      | % Stmts | % Branch | % Funcs | % Lines | Uncovered Line #s 
----------|---------|----------|---------|---------|-------------------
All files |   93.75 |       50 |     100 |   92.85 |                   
 app.js   |   93.75 |       50 |     100 |   92.85 | 17                
----------|---------|----------|---------|---------|-------------------
Test Suites: 1 passed, 1 total
Tests:       2 passed, 2 total
Snapshots:   0 total
Time:        1.299 s
Ran all test suites.
Force exiting Jest: Have you considered using `--detectOpenHandles` to detect async operations that kept running after all tests finished?
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy)
[Pipeline] script
[Pipeline] {
[Pipeline] echo
🚀 Desplegando aplicación...
[Pipeline] bat

C:\ProgramData\Jenkins\.jenkins\workspace\Prueba_Pipeline>npm start  

> ci_pipeline_project@1.0.0 start
> node app.js

Servidor corriendo en http://localhost:3000
```