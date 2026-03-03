# Visualização Parametrizada de Atmosferas Exoplanetárias no Blender

[![Blender Version](https://img.shields.io/badge/Blender-4.0+-orange.svg)](https://www.blender.org/)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

Este repositório contém os modelos 3D, materiais procedurais e configurações de renderização desenvolvidos como parte do artigo **"Blender como Laboratório Virtual para a Criação de Visualizações do Espalhamento em Atmosferas Planetárias"**, submetido à *Revista Brasileira de Ensino de Física* (RBEF). 

O projeto apresenta um *framework* computacional de código aberto que funciona como um laboratório virtual acessível. Ele permite que estudantes, educadores e pesquisadores explorem quantitativamente os efeitos de parâmetros físicos sobre fenômenos ópticos atmosféricos em exoplanetas, utilizando o motor de renderização Cycles do Blender.

![Comparação de Pôres do Sol]([Link_para_a_imagem_dos_pores_do_sol_Marte_Terra_Venus_na_pasta_showcase])
*Simulação do pôr do sol sob três condições atmosféricas distintas: Marte (espalhamento Mie frontal), Terra (espalhamento Rayleigh) e Vênus (luz altamente difusa).*

## 🔭 Recursos e Implementações Físicas

O *framework* traduz dados observacionais e conceitos de transferência radiativa em representações visuais consistentes, implementando:

* **Regimes de Espalhamento:** Simulação explícita do espalhamento de Rayleigh ($\lambda^{-4}$) e aproximações avançadas para o espalhamento de Mie (utilizando generalizações de Henyey-Greenstein).
* **Irradiância Estelar:** Parametrização do tipo espectral da estrela hospedeira (e.g., Anãs M, G e Gigantes B) por meio da conversão da temperatura de corpo negro ($T_{eff}$) via Lei de Planck.
* **Densidade Atmosférica:** Controle da espessura óptica e da extensão atmosférica manipulando a altura de escala molecular ($H_0$) e a densidade de referência ($\rho_0$).
* **Modelagem Procedural:** Geração algorítmica de continentes, oceanos, nuvens volumétricas e camadas atmosféricas (texturas Worley e ruídos Perlin).

## 📁 Estrutura do Repositório

* `/models`: Contém os arquivos `.blend` principais.
* `/renders`: Imagens de alta resolução e renderizações dos experimentos detalhados no artigo.

## ⚙️ Pré-requisitos e Uso

1.  **Software:** [Blender 4.0](https://www.blender.org/download/) ou superior.
2.  **Motor de Renderização:** Cycles (Obrigatório para o cálculo de *Path Tracing* volumétrico).
3.  **Addons Opcionais:** Para a execução estrita dos cenários de superfície, foi utilizada a extensão *Physical Starlight and Atmosphere (PSA)*.

**Como explorar os parâmetros:**
Ao abrir os arquivos `.blend`, navegue até o editor de materiais (*Shader Editor*). Os principais parâmetros físicos (Temperatura da Estrela, $H_0$, Fator de Assimetria $g$ para aerossóis) estão mapeados em nós de valor agrupados para fácil manipulação, permitindo a visualização em tempo real das alterações na composição química e estelar.

