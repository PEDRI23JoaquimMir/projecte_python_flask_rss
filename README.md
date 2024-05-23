# Aplicació de Notícies amb Flask UF3-Projecte

Aquesta aplicació creada a M04 permet veure notícies de diverses seccions de La Vanguardia en una interfície web. El projecte està desenvolupat amb Flask, un microframework de Python.

## Requisits

- Python 3.7 o superior
- pip (gestor de paquets de Python)

## Configuració de l'entorn virtual

Pel que tinc entès, per aïllar les dependències del projecte, és recomanable utilitzar un entorn virtual, suposo que es obligatori fer-ho amb entorn.

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

En aquest mode, l'aplicació utilitza els fitxers XML que he descarregat prèviament que es troben a la carpeta `rss/lavanguardia`.

Per canviar entre els dos modes, modifico la funció `get_rss_lavanguardia` a `app.py`:

```python
def get_rss_lavanguardia(seccio):
    
    # MODE LOCAL: Comenta la següent línia per desactivar el mode local
    xml = f"./rss/lavanguardia/{seccio}.xml"
    
    rss = feedparser.parse(xml)
    return rss
```


## Funcionalitats implementades

### Barra de navegació: 
La pàgina principal (index.html) conté una barra de navegació que permet accedir a les diferents seccions de notícies. Aquesta barra de navegació també es troba a les pàgines de les diferents seccions per facilitar la navegació sense haver de tornar enrere.

### Carousel d'imatges:
A la pàgina principal hi ha un carousel d'imatges que mostra diverses imatges representatives.

### Visualització de notícies: 
Les notícies es mostren en un disseny responsiu. A la pàgina lavanguardia.html, les notícies es disposen en una quadrícula (grid) que varia segons la mida de la pantalla: 1 columna per pantalles petites, 2 columnes per pantalles mitjanes, 3 columnes per pantalles grans i 4 columnes per pantalles molt grans.


## Scripts utilitzats

Per millorar la funcionalitat i el disseny de l'aplicació, he utilitzat scripts externs de Bootstrap i jQuery. Aquests scripts són necessaris per al funcionament correcte del carousel i altres components de la interfície d'usuari. Els scripts inclosos són:

### jQuery: Llibreria JavaScript necessària per a Bootstrap.

```
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
```


### Popper.js: Llibreria per gestionar popups i tooltips, utilitzada per Bootstrap.

```
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js">
```

### Bootstrap JS: Llibreria JavaScript de Bootstrap per a components interactius com el carousel.

```
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js">
```

## Conclusions

Durant el desenvolupament d'aquest projecte, he après utilitzar Flask per crear l'aplicacions web, Configurar i treballar amb entorns virtuals a Python, Fer servir plantilles HTML amb Jinja per generar contingut dinàmic, Implementar dissenys responsius utilitzant Bootstrap, Gestionar el contingut RSS amb la llibreria feedparser, Implementar una barra de navegació coherent a través de diferents pàgines per millorar l'experiència d'usuari.
