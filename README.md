
> # **Treinamento_Azure**

## proteger uma conta de armazenamento, contra exclusão acidental usando um bloqueio de recurso


  Os bloqueios de recursos ajudam a impedir a exclusão acidental dos recursos do Azure.
Para fazer isso criaremos um grupo de recursos no portal do Azure. Considere um grupo de recurso como um contêiner para recursos relacionados do Azure.
Em seguida adcionaremos um bloqueio ao grupo de recursos e confirmaremos se ele não pode ser excluido
  Adicionaremos uma conta de armazenamento ao grupo de recurso e veremos como o bloqueio do grupo de recursos pai impede a exclusão da conta de armazenamento. Uma conta de armazenamento é um contêiner que agrupa um conjunto de serviços do armazenamento do Azure.


## Criando um grupo de recursos
1. Acesse o portal do Azure
2. Na parte superior da página, selecione **Grupos e recursos**.
3. Selecione **+Novo**. **Cria um grupo de recursos**. 
4. Na guia **Básico** preencha os campos conforme figura abaixo.

![001](https://user-images.githubusercontent.com/49000442/139307373-26eabdd2-e538-4a72-9da4-6d6144bdd8d1.JPG)

5. Selecione **Examinar + Criar** e, em seguida, selecione Criar.

 ## Adicionar um bloqueio ao grupo de recursos

1. No portal do Azure, selecione o grupo de recursos **my-test-rg**.
2. Em **Configurações**, selecione **Bloqueios** e **Adcionar**.

![02](https://user-images.githubusercontent.com/49000442/139314392-95b5554b-e665-4def-86d1-5b4bfccb4f3c.JPG)

3. Preencha estes campos

![03](https://user-images.githubusercontent.com/49000442/139315184-cb61a061-3483-4324-9f2d-da82ec2a72d9.JPG)

4. Selecione **OK**

![04](https://user-images.githubusercontent.com/49000442/139315202-033ab04c-7e7b-49e6-9439-5aceeff4a096.JPG)

Você vera que o bloqueio de recurso foi aplicado ao grupo de recursos.

## **Confirmar se o grupo de recursos está protegido contra exclusão**
Aqui, vamos confirmar a proteção tentando excluir o grupo de recursos.

1. Na parte superior da página, selecionamos **my-test-rg** para acessar a página de visão geral do grupo de recursos.
