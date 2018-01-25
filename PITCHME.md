# digiSUS Gestor Geo

### Interfaces e construção de mapas

---

## Interfaces

<br>

- Mapa da Saúde
- Mapas Especiais
- Mapas Incorporados em Painéis

---

---

## Mapa da Saúde
![Mapa da Saúde](/assets/image/mapadasaude.png)


---

## Incluir camadas

```php
							layers : {
								//array com a lista dos layers que serao adicionados e ligados (visiveis)
                                add : ['mapadasaude_setores_censitarios','mapadasaude_municipios_2010','mapadasaude_nomes_municipios_2010','limites_regiao_saude','mapadasaude_cnes','cnes_ativo_inativo',
                                        'cnes_qt_leitos',
                                        'cnes_st_atend_ambulatorial',
                                        'cnes_st_atend_hospitalar',
                                        'cnes_st_centro_cirurgico',
                                        'cnes_st_centro_neonatal',
                                        'cnes_st_centro_obstetrico',
                                        'cnes_st_servico_apoio',
                                        'cnes_tp_gestao',
                                    ],
								//array com a lista dos layers que serao adicionados mas nao ligados
								on : ['mapadasaude_municipios_2010'],
								//array com os layers desligados
                                off : ['mapadasaude_setores_censitarios','mapadasaude_nomes_municipios_2010','limites_regiao_saude','mapadasaude_cnes','cnes_ativo_inativo',
                                        'cnes_qt_leitos',
                                        'cnes_st_atend_ambulatorial',
                                        'cnes_st_atend_hospitalar',
                                        'cnes_st_centro_cirurgico',
                                        'cnes_st_centro_neonatal',
                                        'cnes_st_centro_obstetrico',
                                        'cnes_st_servico_apoio',
                                        'cnes_tp_gestao',]
							},
							//lista de coordenadas x e y que serao adicionadas como pontos no mapa
							points : {
								//array com a lista de coordenadas
								coord : [],
								//titulo da nova camada
								title : ""
							},
							//lista de coordenadas x e y que serao adicionadas como linhas no mapa
							lines : {
								//array de arrays com a lista de coordenadas de cada linha
								//exemplo [[-54,-12,-50,-12],[-50,-1,-50,-2,-50,-3]]
								coord : [ [] ],
								//titulo da nova camada
								title : ""
							},
							//lista de coordenadas x e y que serao adicionadas como poligonos no mapa
							polygons : {
								//array de arrays com a lista de coordenadas de cada poligono. A primeira coordenada deve ser igual a ultima.
								//exemplo [[-50,-1,-48,-2,-50,-3,-50,-1]]
								coord : [ [] ],
								//titulo da nova camada
								title : ""
							},
							//insere elementos no mapa com coordenadas definidas em wkt
							wkt : {
								//string no formato wkt
								coord : "",
								//titulo da nova camada
								title : ""
							},
							//simbolo que sera utilizado para desenhar os elementos inseridos
							symbol : {
								//codigo do simbolo conforme definido em i3geo/symbols
								name : "",
								//em rgb, exemplo "0 255 0"
								color : "",
								//em pixels
								size : ""
							},
							//arquivo KML que sera incluido no mapa. Valido apenas na interface google maps
							kml : {
								url : ""
							},
							//endereco de um WMS (sera incluido como uma camada no mapa)
							wms : {
								url : "",
								layer : "",
								style : "",
								title : "",
								srs : "",
								imagetype : "",
								version : ""
							},
							//filtros que serao aplicados aos layers. Utilize a expressaso conforme definido na documentacao
							//do mapserver, exemplo
							//{layer: "_lbiomashp",expression: "(('[CD_LEGENDA]'='CAATINGA'))"} ou {layer: "_lbiomashp",expression: "cd_legenda='CAATINGA'"}
							filters : [ {
								layer : "",
								expression : ""
							} ],
							//id de um mapa salvo e que sera recuperado
							restoreMapId : ""
						};
```
---?code=src/go/server.go&lang=golang&title=Golang File

@[1,3-6](Present code found within any repo source file.)
@[8-18](Without ever leaving your slideshow.)
@[19-28](Using GitPitch code-presenting with (optional) annotations.)

---

@title[JavaScript Block]

<p><span class="slide-title">JavaScript Block</span></p>

```javascript
// Include http module.
var http = require("http");

// Create the server. Function passed as parameter
// is called on every request made.
http.createServer(function (request, response) {
  // Attach listener on end event.  This event is
  // called when client sent, awaiting response.
  request.on("end", function () {
    // Write headers to the response.
    // HTTP 200 status, Content-Type text/plain.
    response.writeHead(200, {
      'Content-Type': 'text/plain'
    });
    // Send data and end response.
    response.end('Hello HTTP!');
  });

// Listen on the 8080 port.
}).listen(8080);
```

@[1,2](You can present code inlined within your slide markdown too.)
@[9-17](Displayed using code-syntax highlighting just like your IDE.)
@[19-20](Again, all of this without ever leaving your slideshow.)

---?gist=onetapbeyond/494e0fecaf0d6a2aa2acadfb8eb9d6e8&lang=scala&title=Scala GIST

@[23](You can even present code found within any GitHub GIST.)
@[41-53](GIST source code is beautifully rendered on any slide.)
@[57-62](And code-presenting works seamlessly for GIST too, both online and offline.)

---

## Template Help

- [Code Presenting](https://github.com/gitpitch/gitpitch/wiki/Code-Presenting)
  + [Repo Source](https://github.com/gitpitch/gitpitch/wiki/Code-Delimiter-Slides), [Static Blocks](https://github.com/gitpitch/gitpitch/wiki/Code-Slides), [GIST](https://github.com/gitpitch/gitpitch/wiki/GIST-Slides) 
- [Custom CSS Styling](https://github.com/gitpitch/gitpitch/wiki/Slideshow-Custom-CSS)
- [Slideshow Background Image](https://github.com/gitpitch/gitpitch/wiki/Background-Setting)
- [Slide-specific Background Images](https://github.com/gitpitch/gitpitch/wiki/Image-Slides#background)
- [Custom Logo](https://github.com/gitpitch/gitpitch/wiki/Logo-Setting) [TOC](https://github.com/gitpitch/gitpitch/wiki/Table-of-Contents) [Footnotes](https://github.com/gitpitch/gitpitch/wiki/Footnote-Setting)

---

### Template Versions

- #### [Base Template  @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/black)
- #### [Code Maximized @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/black?p=codemax)
- #### [Speaker Notes @fa[external-link gp-download]](https://gitpitch.com/gitpitch/templates/black?p=speaker)

---

### Questions?

<br>

@fa[twitter gp-contact](@gitpitch)

@fa[github gp-contact](gitpitch)

@fa[medium gp-contact](@gitpitch)

---?image=assets/image/gitpitch-audience.jpg&opacity=100

@title[Download this Template!]

### Get your presentation started!
### [Download this template @fa[external-link gp-download]](https://gitpitch.com/template/download/black)

