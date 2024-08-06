# EyeTracker_PIBIC

Um aplicativo android que utiliza a cãmera frontal do celular para o rastreamento da posição da pupila relativa à tela. Possui potencial para o diagnóstico de certas condições neurológicas como autismo, ansiedade social e Parkinson, por exemplo.

Projeto ligado à pesquisa PIBIC-EM ["Sistema de rastreamento ocular baseado em smartphone"](/Resumo%20XI%20ENIC_Pedro%20Nicholas%20Saraiva%20de%20Oliveira.pdf), apresentado no [11º Encontro de Iniciação Científica do Ensino Médio da UFPE (11º ENIC)](https://www.ufpe.br/iniciacao-cientifica/noticias/-/asset_publisher/chRKcuCC0pHt/content/propesqi-realiza-o-30-conic-o-14-coniti-e-o-11-enic-de-22-a-24-deste-mes/40615).

Este projeto é um fork de [Pupil_Detction_App](https://github.com/pramod722445/Pupil_Detection_App). O repositório base contém a implementação da segmentação dos olhos e uma identificação da pupila via tresholding. Este agumenta a segmentação da pupila e adiciona um método para seu rastreamento. 

![](/EyetrackerEx.png)

## Metodologia

O projeto foi concebido em Android Studio e linguagem Java, e utiliza a biblioteca de processamento de imagens e visão computacional [OpenCV](https://opencv.org/). São empregadas técnicas de machine learning para segmentação da face e das regiões dos olhos, a partir do algoritmo de [Viola-Jones](https://en.wikipedia.org/wiki/Viola%E2%80%93Jones_object_detection_framework), e [técnicas morfológicas](https://docs.opencv.org/4.x/d9/d61/tutorial_py_morphological_ops.html) para a segmentação das pupilas. A posição de uma das pupilas em relação à tela é então rastreada depois de uma calibração inicial.

## Principais dependências

- [app/src/main/java/com/example/imagepro](/app/src/main/java/com/example/imagepro)
  - [MainActivity.java](app/src/main/java/com/example/imagepro/MainActivity.java) - tela inicial do aplicativo (câmera desligada)
  - [CameraActivity.java](app/src/main/java/com/example/imagepro/CameraActivity.java) - tela onde a câmera é ligada e ocorrem todos os algoritmos de segmentação e rastreamento
-  [app/src/main/res/layout](app/src/main/res/layout) - arquivos xml que ajustam o layout da tela em cada instância (MainActivity e CameraActivity)

## Uso

> [!WARNING]
> Uma instalação do [Android Studio](https://developer.android.com/studio?hl=pt-br) é necessária para utilização do app

[Faça o download do zip](https://github.com/Agiliis/EyeTracker_PIBIC/archive/refs/heads/FullEyeTracker.zip) ou clone o repositório via git:
```
git clone https://github.com/Agiliis/EyeTracker_PIBIC.git
```
Não é necessário instalar o SDK do OpenCV à parte.

Então abra o projeto no Android Studio e o depure como apk para um celular virtual ou um celular físico.</br> [Como fazer build e rodar seu app (artigo em inglês)](https://developer.android.com/studio/run)

Os dados do rastreamento virão na forma de log no Android Studio.

## Colaboradores

- [pramod722445](https://github.com/pramod722445) - usuário que fez o repositório de fork [Pupil_Detction_App](https://github.com/pramod722445/Pupil_Detection_App)
- Dr. Diógenes Soares Moura - docente do Colégio de Aplicação, UFPE - <diogenes.moura@ufpe.br>
- Dr. Renato Evangelista de Araújo - docente do Departamento de Eletrônica e Sistemas - CTG - UFPE - <renato.earaujo@ufpe.br>

## Agradecimentos

Agradeço ao CNPq pelo apoio financeiro e a UFPE pela oportunidade. Agradeço também ao Dr. Renato E. de Araujo e ao professor Dr. Diógenes S. Moura pela assistência
para a completude deste projeto.
