# Realidade-Aumentada-Unity

## 1. Configuração do projeto Unity:

Para desenvolver uma aplicação de Realidade Aumentada, é necessário primeiro criar um projeto Unity. O Unity é uma plataforma de desenvolvimento de jogos, que, para suportar a realidade aumentada, precisa adicionar pacotes externos, como por exemplo o Vuforia, o qual permite, fazer reconhecimento de imagem e rastreamento de objetos em tempo real.

![image](https://user-images.githubusercontent.com/84996847/223276276-b2492b19-ac50-4173-95e0-0cf0039b6967.png)

## 2. Criação do modelo 3D: 

É necessário criar um objeto 3D que possa ser usado como objeto de realidade aumentada, que será rastreado pelo Vuforia. Esse objeto pode ser criado no Unity usando suas ferramentas de modelagem 3D ou pode ser importado de outras fontes, como programas de modelagem 3D externos. 

- 1 - Crie um novo projeto Unity;
- 2 - Clique com o botão direito do mouse no painel "Hierarquia" e selecione "3D Object" -> "Cube";
- 3 - Um cubo branco será adicionado na tela;
- 4 - Com o cubo selecionado, você pode ajustar suas propriedades no painel "Inspector", como o tamanho, cor e textura;
- 5 - Você pode mover o Cubo usando as Setas de X, Y ou Z presente no plano, ou atráves das propriedades.

![image](https://docs.unity3d.com/es/530/uploads/Main/PrimitiveCube.png)
> Exemplo de Cubo no Unity

## 3. Configuração do Vuforia:

O primeiro passo para começar o desenvolvimento de realidade aumentada no Unity, é configurar o Vuforia. Para isso:

- 1 - Crie uma conta no portal do desenvolvedor no site da Vuforia: [Criar Conta Vuforia](https://developer.vuforia.com/user/login?url=/downloads/sdk%3F_%3D1678117884);
- 2 - Crie uma licença;
- 3 - Crie um banco de dados de imagens, para ser rastreado, chamado de Target, e configure os parametros de detecção como a sensibilidade à luz, o tamanho mínimo da imagem e a velocidade de rastreamento;
- 4 - Faça o Download do TARGET + Features:

![image](https://raw.githubusercontent.com/Rafael-Barbosa/Realidade-Aumentada_Unity/main/Img/Target.png)
> Exemplo de Target

## 4. Vinculação do modelo 3D com o Vuforia: 

Depois do seu modelo 3D criado no Unity, é necessário vinculá-lo com o Vuforia. 
- 1 - Crie um objeto de imagem virtual no unity, adicionando seu target o qual será usado para representar o que será rastreado pelo Vuforia;
- 2 - O modelo 3D deve então ser anexado ao objeto de imagem virtual (Adicionar na mesma pasta);
- 3 - Imprima seu Target, e demonstre na webcam do seu desktop após iniciar o projeto do Unity;
- 4 - Quando a impressao real (impressão) é detectada pelo Vuforia (pela câmera) o objeto 3D é exibido em realidade aumentada, sobrepondo a impressão.

![image](\\imagem\Cubo + Target.png)


