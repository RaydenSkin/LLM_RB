# LLM_RB
REpositorio de trabajo con modelos de lenguaje largo usando ollama

#1. Instalación
como primer paso descargamos [ollama](https://ollama.com/download/linux) de su pagina web

````bash
curl -fsSL https://ollama.com/install.sh | sh
````

##2. Ejecutar el servidor
ejecutar el servidor de APi Rest de ollama con el sigueinte comando
```` bash
ollama serve
````

##3. Descargar un modelo

Crear una nueva consola para ejecutar lo siguiente

En la pagina de ollama descarga un [modelo](https://ollama.com/library) utiliza el siguiente comando:

````bash
ollama pull tinyllama
````
###Listar ias

Ver modelos instalados 
```` bash
ollama list
````
###Ejecutar consultas sobre un modelo
````bash
ollama run tinyllama why sky is blue?
````



##4. Realizar un request a la API REST

emitir y que me retorne una respuesta (metodo) (/URI"URL") (datos)

```` 
post /api/generate
````

````bash
curl -X POST http://localhost:11434/api/generate -d '{"model":"tinyllama","prompt": "why is the sky blue?"}'
````

para que la salida la alamcene en un archivo y ver la cantidad de tokens(mode stream)
````bash
curl -X POST http://localhost:11434/api/generate -d '{"model":"tinyllama","prompt": "why is the sky blue?"}' -o salida.md
````

para que la salida se entrege completa y no por tokens

````bash
curl -X POST http://localhost:11434/api/generate -d '{"model":"tinyllama","prompt": "why is the sky blue?", "stream": false}' -o salida.md
````

##5. guardar informacion de git
````bash
git add .
git commit -m "UPDATED README.md"
git push origin
````


##webgracia
* [ejemplo de readme.md](https://github.com/salvadorhm/introduccion_ia_generativa/wiki)

* [Introduccion a OLLAMA](https://github.com/salvadorhm/introduccion_ia_generativa/wiki/3.-Introducci%C3%B3n-a-Ollama)

* [documentacion API OLLAMA](https://github.com/ollama/ollama/blob/main/docs/api.md)


