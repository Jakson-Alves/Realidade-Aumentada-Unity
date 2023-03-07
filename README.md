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

![image](https://raw.githubusercontent.com/Jakson-Alves/Realidade-Aumentada-Unity/main/imagem/Cubo%20%2B%20Target.png)

## 5. Implementação do script de rastreamento:

Para rastrear o objeto real e atualizar a posição do modelo 3D no mundo virtual do Unity, é necessário implementar um script de rastreamento no Unity. 

- 1 - Selecione o cubo na cena e, em seguida, abra o painel "Inspector" no lado direito da tela;
- 2 - No painel "Inspector", clique no botão "Add Component";
- 3 - Na lista de componentes, selecione "New Script";
- 4 - Com o novo script selecionado no painel "Inspector", clique no botão "Edit Script" para abrir o editor de scripts do Unity;
- 5 - Escreva o código para rotacionar o cubo:
```sh
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class rotate : MonoBehaviour
{
    public Vector3 rotateAmount;
    void Start()
    {
        
    }

    void Update()
    {
        transform.Rotate(rotateAmount * Time.deltaTime);
    }
}
```
>_Script para rotacionar o cubo 3D._
- 6 - Adicione esse Script ao cubo movendo até ele:
- 7 - No novo componet criado, adicione uma rotação em "Rotate Amount" como por exemplo:
```sh
X = 50, Y = 50, Z = 50.
```
![image](https://raw.githubusercontent.com/Rafael-Barbosa/Realidade-Aumentada_Unity/main/Img/Detalhes.png)
>_Valores para rotacionar o cubo 3D._

## 6. Configuração da interface do usuário:

O script pode ser personalizado para controlar a interação do usuário com o modelo 3D de forma intuitiva e agradável, como permitir que o usuário mova e redimensione o objeto.

- 1 - Selecione o cubo na cena e, em seguida, abra o painel "Inspector" no lado direito da tela;
- 2 - No painel "Inspector", clique no botão "Add Component";
- 3 - Na lista de componentes, selecione "New Script";
- 4 - Com o novo script selecionado no painel "Inspector", clique no botão "Edit Script" para abrir o editor de scripts do Unity;
- 5 - Escreva o código para rotacionar o cubo:
```sh
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Movimento : MonoBehaviour
{
    // Start is called before the first frame update
    Vector3 Vec;
    void Start()
    {

    }
    // Update is called once per frame
    void Update()
    {
        Vec = transform.localPosition;
        Vec.y += Input.GetAxis("Jump") * Time.deltaTime * 5;
        Vec.x += Input.GetAxis("Horizontal") * Time.deltaTime * 5;
        Vec.z += Input.GetAxis("Vertical") * Time.deltaTime * 5;
        transform.localPosition = Vec;
    }
}
```
>_Script para adicionar interação do usuário com o cubo 3D._

- 6 - Adicione esse Script ao cubo movendo até ele:
- 7 - Por fim, o usuário conseguirá mover o cubo utilizando as teclas de movimento do teclado, e fazer com que ele "pule" usando a tecla de "Espaço";

![image](./imagem/Movimento.gif)
>_Usuário interagindo com o cubo 3D._

## 7. Adicionando gravidade:

Também é possível adicionar ao cubo gravidade:

- 1 - Selecione o cubo na cena e, em seguida, abra o painel "Inspector" no lado direito da tela;
- 2 - No painel "Inspector", clique no botão "Add Component";
- 3 - Na lista de componentes, selecione "Physics";
- 4 - Seleciona a opção "Rigidbody":
- 5 - Ajuste a altura do seu cubo no plano, e inicie o Unity;
- 6 - Ative a gravidade e veja o cubo caindo:

![image](https://github.com/Jakson-Alves/Realidade-Aumentada-Unity/blob/main/imagem/Gravidade.gif)
>_Usando gravidade com o cubo 3D._
