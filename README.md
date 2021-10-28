
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

![05](https://user-images.githubusercontent.com/49000442/139316505-50356797-24ff-42a2-872a-b3e398e5c45f.JPG)

2. Selecione **Excluir grupo de recursos**.

![06](https://user-images.githubusercontent.com/49000442/139316547-e176951e-7506-4959-9b81-282ffc102718.JPG)

3. No aviso, insira **my-test-rg** e selecione **OK**

Veremos uma mensagem que informa que o grupo de recursos está bloqueado e não podera ser excluído.
![07](https://user-images.githubusercontent.com/49000442/139316576-b0903032-a840-4baa-9050-34f21e596ab5.JPG)

## **Protege uma conta de armazenamento contra exclusão acidental**
Aqui, adcionaremos uma conta de armazenamento ao grupo de recursos e veremos como o bloqueio do grupo de recursos pai impede a exclusão da conta de armazenamento.

1. No portal do Azure, na parte superior da página, selecionamos **Página Inicial** para voltar à página inicial.
2. Selecionamos **Contas de armazenamento**. Em seguida, +**Novo**. A página **Criar conta de armazenamento** é exibida.
3. Na guia **Básico**, preenchemos os campos conforme imagem 

**Observação
Substituimos NNN por uma série de números. Os números ajudam a fazer com que o nome da conta de armazenamento seja exclusivo.

![08](https://user-images.githubusercontent.com/49000442/139319543-72e521b1-3469-42f4-9ebe-6b8c14c940de.JPG)

Como antes, também podemos selecionar uma região que esteja mais perto de nossa localidade

4. Selecionamos **Examinar + Criar** e, em seguida, selecionamos **Criar**.
"*A implantação pode levar alguns minutos para ser concluída."
5. Selecionamos **Ir para o recurso**.
6. Na parte superior da página, selecionamos **Excluir**.

![09](https://user-images.githubusercontent.com/49000442/139319568-84162e4c-f561-4c00-be75-b12715ef84ae.JPG)

agora aparecera uma mensagem informando que o recurso ou o pai dele está bloqueado e não pode ser excluído. Este é um exemplo que mostra a mensagem de erro para uma conta de armazenamento chamada **mysa1234**.

![10](https://user-images.githubusercontent.com/49000442/139319618-49625662-8ae3-4a4c-b367-cc2869a7c1a0.JPG)

Embora não tenhamos criado um bloqueio especifico para a conta de armazenamento, o bloqueio criado para o grupo de recursos pai impede a exclusão do recurso. em outras palavras, a conta de armazenamento herda o bloqueio do grupo de recurso pai.

## **Excluir o grupo de recursos e a conta de armazenamento**
Ao excluir um grupo de recurso, também excluimos os recursos filho, como a conta de armazenamento criada anteriormente. Para excluir o grupo de recursos, primeiro temos que remover o bloqueio de recurso.
1. Selecionamos **Página Inicial > Grupos de recursos > my-test-rg** para acessar o grupo de recursos.
2. Em **Configurações**, selecionamos **Bloqueios**.
3. Localizamos **rg-delete-lock** e escolhemos **Excluir grupo de recurso**.
4. Selecionamos **Visão geral** e escolhemos **Excluir grupo de recursos**.
5. No aviso, insira **my-test-rg** e selecionamos **OK**.

A operação de exclusão pode levar alguns minutos para ser concluida.

6. Quando a operação de exclusão for concluída, selecionamos **Página Inicial > Grupos de recursos**.

veremos agora que o grupo de recursos **my-test-rg** não existe mais na conta. e a conta de armazenamento também foi excluida.
