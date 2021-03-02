 **Table of Contents**

[TOCM]

[========]

# gitcrypt-test-repo
Este repositorio contiene unos archivos de prueba que utilizan git-crypt para el cifrado de contenido de archivos del repositorio.



## Instalaciones

1. GPG en windows.
Para la instalación de GPG en windows se debe ir al siguiente link https://www.gpg4win.org/. Esta instalación ofrece una interface gráfica llamada kleopatra para la administración de las llaves. Sin embargo, también soporta los comandos básicos de GPG 

`gpg --list-keys`

    ------------------------------------------------------
    pub   rsa4096 2020-11-20 [SC] [caduca: 2022-11-19]
		  XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    uid        [  absoluta ] ricardo andres vargas martinez <godxvincent@gmail.com>
    sub   rsa4096 2020-11-20 [E] [caduca: 2022-11-19]
    
    pub   rsa3072 2020-11-21 [SC] [caduca: 2022-11-21]
          XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
    uid        [  absoluta ] ricardo andres vargas <godxvincent@hotmail.com>
    sub   rsa3072 2020-11-21 [E] [caduca: 2022-11-21]

2. git-crypt en windows
Para instalar esto en windows se debe ir al siguiente link https://github.com/oholovko/git-crypt-windows/tags de aqui se puede descargar el instalador en .exe y colocarlo en la misma carpeta de git en la que se encuentra instalado. 

`C:\Program Files\Git\cmd\git-crypt.exe`

Una vez copiado el ejecutable allí ya en la consola de cmd o powershell se podrá usar los comandos para iniciar un repositorio.

## Pasos para inicializar un projecto con git-crypt

1. Se debe crear la llave pgp con kleopatra o por la línea de comandos `gpg --generate-key` donde se solicitará un nombre de usuario,  un correo electronico y un pass phrase.
2. Se debe crear el proyecto
3. Se debe inicializar el proyecto con git-crypt init.
4. Se debe configurar en la raiz del proyecto el archivo `.gitattributes` los archivos o directorios que serán cifrados en github.
`archivos_cifrados/** filter=git-crypt diff=git-crypt`
5. Se debe añadir la llave publica generada en el paso uno 
`git-crypt add-gpg-user XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX`
6. Una vez hecho esto se procede a hacer el push del repositorio a github y ya se verá la ruta cifrada.

## Pasos una vez inicializado un proyecto.

1. Se realiza el git clone
2. Se desbloquea el repositorio en local. `git-crypt unlock`

[========]

