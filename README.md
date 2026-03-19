# Processamento_LiDAR_Nuvem
Estabelecer um procedimento padronizado para download, organização e processamento básico de dados LiDAR, visando gerar produtos derivados da nuvem de pontos para análises ambientais e florestais.

1. Objetivo

Estabelecer um procedimento padronizado para download, organização e processamento básico de dados LiDAR, visando gerar produtos derivados da nuvem de pontos para análises ambientais e florestais.

Produtos finais:
•	Métricas LiDAR (.CVC ou .CSV)
•	Modelos raster (DTM e CHM)
•	Arquivo vetorial de limite da área (shapefile)

2. Fontes de Dados

Os dados LiDAR devem ser obtidos preferencialmente nas seguintes fontes:
•	Serviço Florestal Brasileiro (SFB)
•	Projeto Paisagens Sustentáveis Brasil – Embrapa (PSB)
•	Projeto Estimativa de Biomassa da Amazônia (EBA)

Os dados geralmente são disponibilizados nos formatos:
•	.LAS (LiDAR padrão)
•	.LAZ (LiDAR comprimido)

Também devem ser baixados:
•	Metadados do levantamento
•	Informações de projeção
•	Descrição da missão LiDAR

3. Instalação dos Softwares Necessários

Antes de iniciar o processamento, instalar os seguintes softwares:
•	FUSION – processamento LiDAR
https://forsys.sefs.uw.edu/fusion/fusionlatest.html
•	LAStools – manipulação e conversão de arquivos LiDAR
https://lastools.github.io/
•	Notepad++ – editor de scripts
https://notepad-plus-plus.org/downloads/

3.1 Script de Processamento

Antes da execução do script de processamento, é obrigatório garantir que os seguintes softwares estejam devidamente instalados:
•	FUSION
•	LAStools

Para garantir compatibilidade entre os softwares, recomenda-se que ambos estejam instalados diretamente no diretório raiz do sistema (geralmente C:/)

C:\FUSION
C:\LAStools

3.2 Ajustes em arquivos do FUSION para bom funcionamento

O FUSION (versão 3.40 ou superior) possui suporte à leitura e escrita de arquivos LAS comprimidos (.LAZ) através da biblioteca LASzip, desenvolvida por Martin Isenburg.

Para que essa funcionalidade esteja habilitada, é necessário realizar o seguinte:

1.	Localizar os arquivos de biblioteca LASzip dentro da instalação do LAStools:

LASzip.dll
LASzip64.dll

2.	Copiar ambos os arquivos para o diretório de instalação do FUSION:
				C:\FUSION

Após essa etapa, o FUSION passará a reconhecer diretamente arquivos no formato .LAZ, eliminando a necessidade de conversão prévia para .LAS.

NOTA: Importante sempre observar as considerações nos sites dos desenvolvedores, sempre tem alguma atualização ou alguma solicitação de instalação extra (ou atualização de algum programa).

4. Processamento arquivo 

O processamento dos dados LiDAR deverá ser realizado por meio de script previamente configurado, permitindo a execução automática das etapas de processamento em ambiente MS-DOS (Prompt de Comando do Windows).

O arquivo do script tem o nome:
proa.txt

Trocar “.txt” para “bat”:
proa.bat

Essa alteração transforma o arquivo em um script executável em ambiente MS-DOS. Abaixo está a tela após abrir o arquivo no NotePad++.
 
Figura 1. Print da tela do ProA.bat com o script
O item em destaque em amarelo é o caminho que deve ser alterado toda a vez que for rodar um novo processamento.Esse caminho é onde estará o seu arquivo e o nome do arquivo que será processado. Ele deve ser substituído em todas as linhas do script e pode ser usado o atalho Ctrl + F para “localizer e substituir”
Se tudo processor corretamente, deverão ter os seguintes arquivos gerados na pasta indicada (“C:\FUSION\DATA” para a situação acima)
 
Figura 2. Print da lista de arquivos gerados a partir do “NP_T-0478.Laz” e do srcitp utilizado acima

5. Verificação dos arquivos gerados no GIS
	Abrir os arquivos em um programa GIS (QGis ou ArcGis) para validar os arquivos gerados. Abaixo os itens que devem ser avaliados no programa. Verificar DATUM para que seja aberto de forma correta no programa. Nesse caso o Transecto é da Flona Altamira, FUSO 21S.
 
Figura 3. Print dos arquivos que deverão ser validados no programa GIS
	Deverá ser aberto o shapefile do transescto bem como os 03 rasters gerados para cada grid (36, 50 e 68). As informações relacionadas aos resultados “grids” podem ser consultados no “FUSION_manual.pdf” que se encontra em “C:\FUSION\doc”.
  
Grid 36 – Elevação P90
Grid50 - Percentage all returns above heightbreak
Grid68 - Canopy relief ratio ((mean - min) / (max – min))
 
Figura 4. Print tela ArcGis - Shapefile do Transecto

Avaliando o Grid 36 que seria as alturas das árvores. Fazer uma reclassificaçao e modificar cores para melhor visualização a análise.

 
Figura 5. Print tela ArcGis - distribuição valores altura

 
Figura 6. Print tela ArcGis - Reclassificação cores - raster altura



Dando um ZOOM em determindo ponto apenas para verificar os pontos mais altos com possiveis arvores mais altas na imagem de satélite.
  
Figura 7. Print para conferencia de dados gerados para realidade de imagem satélite - altura árvores

Repetir essa conferencia para os outros dois grids gerados, 50 e 68. Se tudo estiver OK, subir os arquivos gerados para pasta referente ao transecto, a área de estudo e ao ano, no Drive compartilhado.
