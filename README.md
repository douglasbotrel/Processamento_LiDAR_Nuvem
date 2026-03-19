# 📊 Processamento de Dados LiDAR

## 1. 🎯 Objetivo

Estabelecer um procedimento padronizado para **download, organização e processamento básico de dados LiDAR**, visando a geração de produtos derivados da nuvem de pontos para análises ambientais e florestais.

### 📦 Produtos finais

- Métricas LiDAR (`.CVC` ou `.CSV`)
- Modelos raster (**DTM** e **CHM**)
- Arquivo vetorial de limite da área (**Shapefile**)

---

## 2. 🌎 Fontes de Dados

Os dados LiDAR devem ser obtidos preferencialmente nas seguintes fontes:

- Serviço Florestal Brasileiro (**SFB**)
- Projeto Paisagens Sustentáveis Brasil – Embrapa (**PSB**)
- Projeto Estimativa de Biomassa da Amazônia (**EBA**)

### 📁 Formatos disponíveis

- `.LAS` (formato padrão LiDAR)
- `.LAZ` (formato comprimido)

### 📌 Dados complementares obrigatórios

- Metadados do levantamento  
- Informações de projeção  
- Descrição da missão LiDAR  

---

## 3. ⚙️ Instalação dos Softwares

Antes de iniciar o processamento, instale:

- **FUSION** – processamento LiDAR  
  https://forsys.sefs.uw.edu/fusion/fusionlatest.html  

- **LAStools** – manipulação e conversão  
  https://lastools.github.io/  

- **Notepad++** – edição de scripts  
  https://notepad-plus-plus.org/downloads/  

---

## 3.1 🧾 Preparação do Ambiente

Certifique-se de que os softwares estejam instalados:

- FUSION  
- LAStools  

📌 Recomenda-se instalar diretamente no diretório raiz:

C:\FUSION
C:\LAStools

---

## 3.2 🔧 Ajustes no FUSION (Suporte a .LAZ)

O **FUSION (versão 3.40 ou superior)** suporta arquivos `.LAZ` via biblioteca **LASzip**.

### Passos:

1. Localize os arquivos no diretório do LAStools:

LASzip.dll
LASzip64.dll


2. Copie para:
C:\FUSION


✅ Após isso, o FUSION reconhecerá arquivos `.LAZ` sem necessidade de conversão.

> ⚠️ **Nota importante**  
> Sempre verifique os sites oficiais dos desenvolvedores. Atualizações ou dependências extras podem ser necessárias.

---

## 4. ▶️ Processamento dos Dados

O processamento é realizado via script no Prompt de Comando (MS-DOS).

### 📄 Arquivo do script
proa.txt


➡️ Renomear para:
proa.bat


---

### 🛠️ Configuração do Script

- Edite no **Notepad++**
- Atualize o caminho do arquivo LiDAR em **todas as linhas**
- Utilize:
Ctrl + F → Localizar e Substituir


---

### 📂 Saída esperada

Se o processamento ocorrer corretamente, os arquivos serão gerados em:
C:\FUSION\DATA


---


