Yailyn Santana 2025-1104
# Práctica de Automatización con Ansible y Docker

## Descripción

Esta práctica consiste en automatizar la configuración de cinco servidores Ubuntu utilizando Ansible y Docker.

Se utiliza Docker Compose para crear cinco contenedores Ubuntu con un servidor SSH, y Ansible para ejecutar tareas de configuración de manera automática.

## Tecnologías utilizadas

- Docker
- Docker Compose
- Ubuntu 24.04
- Ansible
- SSH
- WSL Ubuntu

## Estructura del proyecto

- `Dockerfile`: configuración de la imagen Ubuntu con SSH.
- `docker-compose.yml`: creación de los cinco servidores.
- `inventario.ini`: inventario de los servidores administrados.
- `ansible.cfg`: configuración de Ansible.
- `playbook.yml`: automatización de las tareas.

## Tareas automatizadas

1. Actualizar la caché de APT.
2. Crear el usuario `itla`.
3. Crear la carpeta `/home/itla/app`.
4. Crear el archivo `hola.txt` dentro de la carpeta.
5. Instalar las aplicaciones `cowsay` y `htop`.

## Ejecución

Crear e iniciar los contenedores:

```bash
docker compose up -d --build
```

Ejecutar el playbook desde WSL Ubuntu, después de configurar el inventario y verificar la conectividad SSH:

```bash
export ANSIBLE_CONFIG="$PWD/ansible.cfg"
ansible-playbook playbook.yml
```

## Resultados

La automatización se ejecutó correctamente en los cinco servidores Ubuntu.

Todos los servidores completaron las tareas sin errores:

- `servidor1`: failed=0
- `servidor2`: failed=0
- `servidor3`: failed=0
- `servidor4`: failed=0
- `servidor5`: failed=0

Se comprobó la creación del usuario `itla`, la carpeta `app`, el archivo `hola.txt` y la instalación de `cowsay` y `htop`.

## Nota

Las credenciales utilizadas son exclusivamente para un entorno local de laboratorio. Las direcciones IP de los contenedores pueden cambiar al recrearlos.
