# 🌡️ Surface Heat Analysis - Em desenvolvimento! 

<!-- project-badges:start -->
![Aplicação: R · Shiny](https://img.shields.io/static/v1?label=Aplica%C3%A7%C3%A3o&message=R%20%C2%B7%20Shiny&color=276DC3&style=flat)
![Status: Em desenvolvimento](https://img.shields.io/static/v1?label=Status&message=Em%20desenvolvimento&color=orange&style=flat)
[![Autoria: Rebeca Diniz Moura](https://img.shields.io/static/v1?label=Autoria&message=Rebeca%20Diniz%20Moura&color=8b5cf6&style=flat)](https://github.com/RebecaGis)
[![Licença: GPL-3.0](https://img.shields.io/static/v1?label=Licen%C3%A7a&message=GPL-3.0&color=blue&style=flat)](https://github.com/RebecaGis/Surface-Heat-Analysis/blob/docs/badges-2026-11-10/LICENSE)
<!-- project-badges:end -->


Aplicativo interativo em **R Shiny** para análise de temperatura de superfície utilizando imagens **Landsat Collection 2 Level 2**.
O app permite identificar áreas quentes em municípios brasileiros, calcular estatísticas de temperatura, gerar mapas interativos e exportar resultados em diversos formatos.

---

## 🚀 Funcionalidades

* **Upload de Dados**

  * Imagens Landsat (GeoTIFF – banda térmica ST_B10).
  * Arquivo GeoJSON do município de interesse.
  * Suporte para múltiplas imagens (1 a 10).

* **Processamento**

  * Conversão automática de **Kelvin → Celsius**.
  * Recorte da cena Landsat com base no município selecionado.
  * Identificação de **áreas quentes** acima do limite definido pelo usuário (default: 35 °C).

* **Resultados**

  * Informações detalhadas sobre os arquivos carregados.
  * Estatísticas descritivas de temperatura (média, mínima, máxima, desvio-padrão).
  * Tabela comparativa entre imagens.
  * Boxplots de comparação temporal.
  * Mapas interativos (**Leaflet**) com destaque das áreas críticas.
  * Visualizações adicionais do município em **ggplot2**.

* **Download**

  * **GeoJSON** com polígonos de áreas quentes.
  * **GeoTIFF** com raster de temperatura em °C.
  * **PNG** dos mapas de temperatura.

---

## 🛠️ Tecnologias Utilizadas

* **R Shiny** + **Shiny Dashboard** (interface web interativa)
* **terra** (processamento de rasters)
* **sf** (geoprocessamento vetorial)
* **leaflet** (mapas interativos)
* **ggplot2** (visualizações gráficas)
* **dplyr, purrr, stringr** (manipulação de dados)
* **osmdata, fs, shinyFiles** (suporte a dados externos e sistema de arquivos)

---

## 📂 Estrutura do App

* **Upload de Arquivos**: envio das imagens Landsat + GeoJSON.
* **Resultados**: análise estatística, mapas interativos e gráficos.
* **Download**: exportação dos outputs processados.

---

## ▶️ Como Executar

1. Clone este repositório:

   ```bash
   git clone https://github.com/seu-usuario/surface-heat-analysis.git
   cd surface-heat-analysis
   ```

2. Abra o R ou RStudio e instale as dependências:

   ```R
   install.packages(c(
     "shiny", "shinydashboard", "terra", "sf", "leaflet", "ggplot2",
     "shinyFiles", "fs", "osmdata", "dplyr", "purrr", "stringr"
   ))
   ```

3. Rode o aplicativo:

   ```R
   shiny::runApp("app.R")
   ```

---

## 📊 Exemplos de Uso

* Avaliar a evolução de áreas urbanas mais quentes (ilhas de calor).
* Comparar diferentes datas de imagens Landsat.
* Quantificar área total de calor crítico (km² e % do município).
* Apoiar diagnósticos em **gestão urbana** e **planejamento ambiental**.

---

## ⚠️ Observações

* O tamanho máximo por arquivo é **500MB**.
* O app espera **Landsat Collection 2 Level 2**, que já contém a banda de temperatura (ST_B10).
* É necessário que os **sistemas de coordenadas** sejam compatíveis.
