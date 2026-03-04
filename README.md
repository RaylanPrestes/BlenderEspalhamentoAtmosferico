# Visualização Parametrizada de Atmosferas Exoplanetárias no Blender

[![Blender Version](https://img.shields.io/badge/Blender-4.0+-orange.svg)](https://www.blender.org/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Este repositório contém os modelos 3D, materiais procedurais e configurações de renderização desenvolvidos como parte do artigo **"Blender como Laboratório Virtual para a Criação de Visualizações do Espalhamento em Atmosferas Planetárias"**, submetido à *Revista Brasileira de Ensino de Física* (RBEF). 

O projeto apresenta um *framework* computacional de código aberto que funciona como um laboratório virtual acessível. Ele permite que estudantes, educadores e pesquisadores explorem quantitativamente os efeitos de parâmetros físicos sobre fenômenos ópticos atmosféricos em exoplanetas, utilizando o motor de renderização Cycles do Blender.

![Planetas sob estrelas de tipos distintos](/render/DiffTemp.png)
*Simulação da aparência de um planeta rochoso sob a luz de estrelas hospedeiras de tipos distintos (Temperaturas Efetivas distintas).*

## 🔭 Recursos e Implementações Físicas

O *framework* traduz dados observacionais e conceitos de transferência radiativa em representações visuais consistentes, implementando:

* **Regimes de Espalhamento:** Simulação explícita do espalhamento de Rayleigh ($\lambda^{-4}$) e aproximações avançadas para o espalhamento de Mie (utilizando generalizações de Henyey-Greenstein).
* **Irradiância Estelar:** Parametrização do tipo espectral da estrela hospedeira (e.g., Anãs M, G e Gigantes B) por meio da conversão da temperatura de corpo negro ($T_{eff}$) via Lei de Planck.
* **Densidade Atmosférica:** Controle da espessura óptica e da extensão atmosférica manipulando a altura de escala molecular ($H_0$) e a densidade de referência ($\rho_0$).
* **Modelagem Procedural:** Geração algorítmica de continentes, oceanos, nuvens volumétricas e camadas atmosféricas (texturas Worley e ruídos Perlin).

## 📁 Estrutura do Repositório

* `/modelos`: Contém os arquivos `.blend` principais.
    * `/Observador_Externo`: Contém os arquivos `.blend` para os modelos do observador externo e planetas rochosos com atmosferas volumétricas.
    * `/Observador_na_Superficie`: Contém os arquivos `.blend` para os modelos do observador na superfície.
* `/renders`: Imagens de alta resolução e renderizações dos experimentos detalhados no artigo.

## ⚙️ Pré-requisitos e Uso

1.  **Software:** [Blender 5.0](https://www.blender.org/download/) ou superior.
2.  **Motor de Renderização:** Cycles (Obrigatório para o cálculo de *Path Tracing* volumétrico).
3.  **Addons Opcionais:** Para a execução estrita dos cenários de superfície, foram utilizadas a extensões *Physical Starlight and Atmosphere (PSA)* e *Physical Open Waters (POW)* (Se os modelos forem executados sem as extensões o resultado é uma tela preta). Uma versão simplificada feita utilizando somente ferramentas nativas do Blender para o modelo superficial pode ser acessada no arquivo `/modelos/Observador_na_Superficie/Superficie-Oceanica-Nativa.blend`, neste modelo é possível replicar os experimentos de variação de temperatura e composição de maneira aproximada. Os modelos volumétricos com observador externo não dependem de nenhum addon adicional e constituem os modelos de maior interesse.

**Como explorar os parâmetros:**
Ao abrir os arquivos `.blend`, navegue até o editor de materiais (*Shader Editor*). Os principais parâmetros físicos ($H_0$, diâmetro $d$ para aerossóis) estão mapeados em nós de valor agrupados para fácil manipulação, permitindo a visualização em tempo real das alterações na composição química e estelar. A Temperatura Efetiva pode ser modificada no material do objeto *Sun*. Os parâmetros para o modelo com observador na superfície podem ser alterados na aba *World* do *Shader Editor*.
