# Aplicació de Notícies amb Flask UF3-Projecte

Aquesta aplicació creada a M04 permet veure notícies de diverses seccions de La Vanguardia en una interfície web. El projecte està desenvolupat amb Flask, un microframework de Python.

## Requisits

- Python 3.7 o superior
- pip (gestor de paquets de Python)

## Configuració de l'entorn virtual

Pel que tinc entès, per aïllar les dependències del projecte, és recomanable utilitzar un entorn virtual.

1. Creo un entorn virtual a la carpeta del projecte:

    ```bash
    python -m venv env
    ```

2. Activo l'entorn virtual (Windows en el meu cas):

    - **Windows:**

        ```bash
        .\env\Scripts\activate
        ```

3. Instal·lo les dependències necessàries:

    ```bash
    pip install -r requirements.txt
    ```

## Inici de l'aplicació

1. M'asseguro que l'entorn virtual està activat.
2. Inicio el servidor Flask:

    ```bash
    flask run
    ```

3. Obro el navegador i vaig a `http://127.0.0.1:5000` per veure l'aplicació en funcionament.

## Ús de l'aplicació

L'aplicació té dues maneres de funcionar: mode remot i mode local. Com diu l'enunciat jo ho faré de forma local.


### Mode local

En aquest mode, l'aplicació utilitza fitxers XML descarregats prèviament que es troben a la carpeta `rss/lavanguardia`.

Per canviar entre els dos modes, modifica la funció `get_rss_lavanguardia` a `app.py`:

```python
def get_rss_lavanguardia(seccio):
    # MODE REMOT: Descomenta la següent línia per utilitzar el mode remot
    # xml = f"https://www.lavanguardia.com/rss/{seccio}.xml"
    
    # MODE LOCAL: Comenta la següent línia per desactivar el mode local
    xml = f"./rss/lavanguardia/{seccio}.xml"
    
    rss = feedparser.parse(xml)
    return rss
```
