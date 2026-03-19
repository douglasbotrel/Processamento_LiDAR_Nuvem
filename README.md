<p align="center">
  <img src="images/treelab_logo.png" width="180"/>
</p>

<h1 align="center">Processamento de Dados LiDAR</h1>

<p align="center">
  <img src="images/ufvjm_logo.png" width="300"/>
</p>

---

## Índice

- [1. Objetivo](#1--objetivo)
- [2. Fontes de Dados](#2--fontes-de-dados)
- [3. Instalação dos Softwares](#3-instalação-dos-softwares)
  - [3.1 Preparação do Ambiente](#31--preparação-do-ambiente)
  - [3.2 Ajustes no FUSION](#32--ajustes-no-fusion-suporte-a-laz)
- [4. Processamento dos Dados](#4-processamento-dos-dados)
- [5. Verificação no GIS](#5-verificação-no-gis)
- [6. Armazenamento](#6-armazenamento)

---

## 1. Objetivo

Estabelecer um procedimento padronizado para **download, organização e processamento de dados LiDAR**, com foco na geração de produtos derivados da nuvem de pontos para análises ambientais e florestais.

### Produtos finais

- Métricas LiDAR (`.CVC` ou `.CSV`)  
- Modelos raster (**DTM** e **CHM**)  
- Arquivo vetorial (**Shapefile**)  

---

## 2. Fontes de Dados

Os dados LiDAR devem ser obtidos, preferencialmente, a partir das seguintes instituições:

- Serviço Florestal Brasileiro (**SFB**)  
- Projeto Paisagens Sustentáveis Brasil – Embrapa (**PSB**)  
- Projeto Estimativa de Biomassa da Amazônia (**EBA**)  

### Formatos disponíveis

- `.LAS` (formato padrão)  
- `.LAZ` (formato comprimido)  

### Dados complementares obrigatórios

- Metadados  
- Sistema de projeção  
- Informações da missão LiDAR  

---

## 3. Instalação dos Softwares

Instalar previamente:

- **FUSION** – processamento LiDAR  
- **LAStools** – manipulação de dados  
- **Notepad++** – edição de scripts  

---

## 3.1 Preparação do Ambiente

Recomenda-se instalar diretamente no diretório raiz:

*`C:\FUSION`*  
*`C:\LAStools`*

---

## 3.2 Ajustes no FUSION (Suporte a .LAZ)

O **FUSION (v3.40+)** suporta `.LAZ` via biblioteca **LASzip**.

### Procedimento

1. Localizar no LAStools:
   - `LASzip.dll`  
   - `LASzip64.dll`  

2. Copiar para:

*`C:\FUSION`*

✅ Após isso, arquivos `.LAZ` serão reconhecidos automaticamente.

> ⚠️ **Nota técnica**  
> Verifique atualizações nos sites oficiais dos desenvolvedores.

---

## 4. Processamento dos Dados

Processamento realizado via script no Prompt de Comando.

### Script

Arquivo original: `proa.txt`  
Renomear para: `proa.bat`

---

### Configuração

- Editar no **Notepad++**  
- Atualizar caminhos do arquivo LiDAR  
- Utilizar: `Ctrl + F → Substituir`

---

### Saída esperada

Arquivos gerados em:

*`C:\FUSION\DATA`*

---

<p align="center">
  <img src="images/proab_script.png" width="700"/>
  <br>
  <b>Figura 1 – Script ProA.bat com destaque para o caminho do arquivo de entrada.</b>
</p>

O caminho destacado deve ser atualizado a cada execução.

---

<p align="center">
  <img src="images/arquivos_gerados.png" width="700"/>
  <br>
  <b>Figura 2 – Arquivos gerados após o processamento LiDAR.</b>
</p>

---

## 5. Verificação no GIS

Validar os dados em ambiente SIG:

- QGIS  
- ArcGIS  

---

<p align="center">
  <img src="images/arquivos_grids.png" width="700"/>
  <br>
  <b>Figura 3 – Arquivos raster e vetoriais para validação.</b>
</p>

---

### Verificações obrigatórias

- Sistema de coordenadas (DATUM)  
- Fuso (ex: 21S)  
- Área correta (ex: Flona Altamira)  

---

<p align="center">
  <img src="images/shape_transecto.png" width="700"/>
  <br>
  <b>Figura 4 – Shapefile do transecto no ArcGIS.</b>
</p>

---

### Análise dos dados

Grid 36 representa altura da vegetação. Recomenda-se reclassificação.

---

<p align="center">
  <img src="images/distri_valores.png" width="700"/>
  <br>
  <b>Figura 5 – Distribuição de valores de altura.</b>
</p>

<p align="center">
  <img src="images/reclassi.png" width="700"/>
  <br>
  <b>Figura 6 – Reclassificação do raster.</b>
</p>

---

### Dados a validar

| Grid | Descrição |
|------|----------|
| 36 | Elevação P90 |
| 50 | Percentual acima do *heightbreak* |
| 68 | Canopy Relief Ratio |

📘 Referência:

*`C:\FUSION\doc\FUSION_manual.pdf`*

---

### Conferência final

- Validar grids (36, 50 e 68)  
- Comparar com imagens de satélite  
- Avaliar coerência dos dados  

---

<p align="center">
  <img src="images/compara1.png" width="350"/>
  <img src="images/compara2.png" width="350"/>
  <br>
  <b>Figura 7 e 8 – Comparação com imagem de satélite para validação da altura da vegetação.</b>
</p>

---

## 6. Armazenamento

Após validação, organizar em repositório:

- Transecto  
- Área de estudo  
- Ano  

---
