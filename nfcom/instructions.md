# NFCom
A **NFCom (Nota Fiscal Fatura de Serviços de Comunicação Eletrônica), modelo 62** é o documento fiscal eletrônico para serviços de comunicação/telecom. Ela **substitui os modelos 21 e 22**, padronizando o faturamento do setor. Foi instituída pelo **Ajuste SINIEF 07/2022** e atualizada por normas posteriores (ex.: **Ajuste SINIEF 34/2024**), com **obrigatoriedade nacional a partir de 01/11/2025**. A validade jurídica decorre da **assinatura digital do emitente** e da **autorização de uso pela SEFAZ**.

> **Importante (visão geral):**  
> • A NFCom **substitui integralmente** os modelos 21/22 a partir de **01/11/2025**.  
> • Antes da obrigatoriedade, **credenciamento e testes** dependem da **SEFAZ do seu Estado**. Entre em contato com a SEFAZ para mais informações.  
> • A emissão **exige certificado digital A1** da empresa.  
{.is-info}

---

## Primeiros passos com NFCom
Tenha um **Certificado Digital modelo A1** válido. De posse do certificado, faça o upload em **Configurações → Certificados**.  
<br>

![2.png](/nota-fiscal/nfcom/nfcom-inicial/2.png)

- Na página de Certificados, clique em **Adicionar certificado**.

![3.png](/nota-fiscal/nfcom/nfcom-inicial/3.png)

Ao clicar em **Adicionar certificado**, será aberto um modal para envio do seu certificado digital:
- **Nome:** identifique o certificado.  
- **Arquivo do Certificado:** clique em **Escolher arquivo** e selecione o A1 (pfx/p12).  
- **Senha:** informe a senha do certificado.  
Em seguida, clique em **Salvar**.

<br>

![4.png](/nota-fiscal/nfcom/nfcom-inicial/4.png)
<br>

Após salvar, a página recarrega com os detalhes do certificado inserido:  
<br>
![5.png](/nota-fiscal/nfcom/nfcom-inicial/5.png)

---

## Selecionando o Certificado
Depois de adicionar, selecione o **certificado que emitirá as NFCom** em **Configurações → Dados da empresa**.  
<br>
![6.png](/nota-fiscal/nfcom/nfcom-inicial/6.png)
<br>
Na seção **Dados cadastrais**, escolha o **Certificado digital** e, ao final da página, clique em **Atualizar dados**.  
<br>
![dados_empresa.png](/nota-fiscal/nfcom/nfcom-inicial/dados_empresa.png)

---

## Adicionando Produtos
Antes de emitir a NFCom, cadastre os **Produtos/Serviços** que serão faturados (serviços oferecidos em seus planos entram aqui para posterior inclusão nas notas).  
Exemplo: o provedor oferece aos clientes **provimento de internet** e **acesso a streamings**. Mesmo com diversos planos/velocidades, há dois produtos principais: **Acesso à internet (SCM)** e **SVA**. Em regra, basta cadastrar esses dois produtos e vinculá-los aos planos conforme a operação do provedor. Caso precise, crie quantos produtos desejar e vincule aos planos conforme sua necessidade.

Acesse **NFCom → Produtos** e clique no botão **Adicionar produto** ao carregar a página.  
<br>
![nfcom_produto_menu.png](/nota-fiscal/nfcom/nfcom-prod-v1/nfcom_produto_menu.png)
<br>

> O Atlaz **não se responsabiliza** por configurações tributárias incorretas. **Consulte sua contabilidade** para parametrizar corretamente cada produto conforme a legislação.  
{.is-danger}

Preencha:
- **Nome** do produto/serviço.  
- **cClass** e **Unidade de medida** conforme orientação da contabilidade.  
- **ICMS, PIS, COFINS, FUST, FUNTTEL** conforme o enquadramento fiscal do serviço.  

> O **CFOP** do produto será importado diretamente do **cadastro do assinante**; ou seja, será aquele informado no respectivo campo **CFOP** da ficha do assinante.  
{.is-danger}

> As regras da NFCom consideram os **tributos no item**. Alguns campos são opcionais; se **não informados**, não constam no XML; se informados com **0**, representam alíquota zero (ex.: benefício fiscal). **Valide com sua contabilidade** conforme o Manual de Orientação ao Contribuinte da NFCom.  
{.is-warning}

Após preencher, clique em **Criar Produto**.  
<br>
![criar_produto2.png](/nota-fiscal/nfcom/nfcom-prod-v1/criar_produto2.png)
<br>
Após salvar, a lista **Produtos** exibirá o item cadastrado:  
<br>
![listagem_produtos.png](/nota-fiscal/nfcom/nfcom-prod-v1/listagem_produtos.png)

---

## Configurando a NFCom
Após cadastrar os produtos, é necessário configurar algumas informações na NFCom.  
<br>
![nfcom_configuracoes11.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/nfcom_configuracoes11.png)
<br>

Na seção **Dados para emissão de NFCom**, preencha/seleciona:
- **Ambiente:** define se as notas serão emitidas em **homologação** ou **produção** (homologação serve para testes e a emissão nesse ambiente **não gera incidência de impostos**).  
- **Série:** por padrão, você poderá selecionar **1** ou **2**.  
- **Número da última NFCom:** caso já tenha emitido notas fora do Atlaz na série selecionada, preencha com o **número da última nota**; se nunca emitiu, deixe em branco.
- **Competência**: Define se na emissão a competencia da nota será referente ao mês de vencimento do boleto ou se será referente ao mês de emissão da nota. 
- **Informações adicionais:** texto livre com observações que você deseja exibir na nota.

Na seção **IBPT**, preencha as informações sobre o imposto conforme orientação da sua contabilidade.

---

## Configurando os produtos
Você pode configurar produtos e definir a porcentagem dos mesmos **na ficha do assinante**, **nos planos** e também **nas configurações da NFCom**.

> A ordem de prioridade é: **Produto na Ficha do Assinante**, **Produto no Plano** e, por último, **Produto nas Configurações da NFCom**.  
{.is-danger}
---

## Configuração padrão por filial
![produtos_criacao_em_massa11.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/produtos_criacao_em_massa11.png)

Na seção **Produtos para criação em massa**, defina a **porcentagem** de cada produto sobre o **valor do boleto** para emissões automáticas ou em lote.  
Exemplo: se o boleto do assinante é **R$ 100,00**, e o produto **SCM – Serviços de Comunicação Multimídia** tem **60%**, a base de cálculo desse produto será **R$ 60,00**. O produto **TIPO SVA**, com **40%**, terá base de **R$ 40,00** — totalizando **R$ 100,00**.

> Essa configuração será o **padrão** para todas as notas emitidas em lote ou automaticamente **quando não houver** configuração de NFCom no **Plano** vinculado ao boleto **ou** personalização na **Ficha do Assinante**. No **próximo tópico**, você verá como definir **porcentagens personalizadas** por assinante e escolher **produtos específicos** no cadastro do cliente (útil para **PJ** ou casos com regras especiais).  
{.is-info}

---

## Configurando ambiente de emissão
Para configurar o ambiente de emissão ( **Produção** ou **Homologação** ), acesse **NFCom → Configurações** e, no campo **Ambiente**, selecione a opção desejada. Em seguida, clique em **Salvar**.

![tipo_ambiente11.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/tipo_ambiente11.png)

> No ambiente de **Homologação**, você pode realizar emissões de teste **sem incidência de impostos**, pois esse ambiente serve apenas para testes. Já no ambiente de **Produção**, a nota é transmitida e possui **valor fiscal**, com **incidência de impostos**.  
{.is-danger}

---

## Configurando os produtos nos planos
Você pode inserir os produtos cadastrados no **Plano**. Dessa forma, o sistema utilizará automaticamente os produtos de acordo com o plano vinculado ao boleto do cliente na **emissão em massa** e na **emissão automática**. Para configurar os produtos no plano, acesse **Configurações → Planos** e selecione o plano que deseja atribuir um ou mais produtos.  
<br>
![config_planos.png](/nota-fiscal/nfcom/nfcom-prod-v1/config_planos.png)

Após clicar para **editar o plano**, localize a seção **Configuração da NFCom** e adicione os produtos referentes ao plano, definindo as **porcentagens** sobre o valor do boleto do cliente.  
<br>
![config_nfcom_planos_enfase2.png](/nota-fiscal/nfcom/nfcom-prod-v1/config_nfcom_planos_enfase2.png)

> Não é necessário criar um produto específico para cada plano. Você pode criar produtos genéricos, como **SCM** e **SVA**, e defini-los nos planos que possuem esses itens. O mesmo vale para planos com **3 ou mais produtos**.  
{.is-info}

> Se o boleto do cliente **não** for criado automaticamente, a vinculação do boleto ao plano ficará indisponível e, portanto, as **configurações do plano não serão aplicadas**. Ao desmarcar a caixa **Calcular valores automaticamente** durante a criação do carnê, o boleto é desvinculado do plano.  
{.is-danger}

---


## Personalizando produto no assinante
Caso deseje configurar assinantes específicos com produtos diferentes dos padrões definidos em **NFCom → Configurações**, localize o **cadastro do assinante** que terá **porcentagens e produtos** diferentes do padrão salvo.

![assinante_fulano_busca.png](/nota-fiscal/nfcom/nfcom-prod-v1/assinante_fulano_busca.png)

Clique em **Editar**.

![editar_fulano.png](/nota-fiscal/nfcom/nfcom-prod-v1/editar_fulano.png)

Role até o final da página e localize as configurações referentes **à NFCom**. Nessa seção, defina os **produtos personalizados** e as **porcentagens** desejadas (os produtos devem estar previamente cadastrados). Depois, clique em **Salvar**.  
<br>

![configuracao_no_assinante11.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/configuracao_no_assinante11.png)

> Esta personalização **sobrescreve** a configuração padrão de **NFCom → Configurações** e também a configuração de NFCom no **Plano**, **apenas para este assinante**.  
> A soma das **porcentagens** não pode ultrapassar **100%** e, caso fique **abaixo de 100%**, o sistema **não completa** automaticamente o restante.  
> Utilize somente quando houver **necessidade contábil**.  
> Alterações aqui **não reprocessam** notas já emitidas; passam a valer **apenas para novas emissões** após salvar.  
{.is-warning}

---

## Criando notas modelo 62 de forma avulsa (NFCom)
Com os produtos cadastrados, acesse **NFCom → Criar**:

![nfcom_avulsa1.png](/nota-fiscal/nfcom/nfcom-prod-v1/nfcom_avulsa1.png)

Na criação da nota avulsa:
- **Cliente:** selecione o tomador do serviço.  
- **Série:** vem da configuração padrão.  
- **Data de competência:** período a que o serviço se refere (base de cálculo).  
- **Data de vencimento:** vencimento da cobrança.  
- **Data de uso:** referência do **período de uso** do assinante.  

Nos **Itens**, adicione os produtos cadastrados, informe o **valor unitário** e, se houver, o **desconto**.  
Finalize em **Criar NFCom**.  
<br>

![nfcom_avulsa_itens.png](/nota-fiscal/nfcom/nfcom-prod-v1/nfcom_avulsa_itens.png)

<br>

Depois, acompanhe o **status** em **NFCom → Notas**:  
<br>

> A **nota avulsa** não é vinculada a boleto. Por isso, **não use porcentagens**: informe **valores** nos campos. Para posicionar a **vírgula** corretamente nas casas decimais, **complete com zeros à direita** até obter o valor desejado.  
{.is-warning}

---

## Criação de notas em massa
Para criar notas em massa, acesse **NFCom → Criar em massa**:  
<br>
![nfcom_criar_massa.png](/nota-fiscal/nfcom/nfcom-prod-v1/nfcom_criar_massa.png)

Depois, **aplique os filtros** (boletos pagos/abertos, por caixa, etc.). Há diversos filtros para facilitar a geração.  
<br>

![filtrar_selecionar_gerar_em_massa.png](/nota-fiscal/nfcom/nfcom-prod-v1/filtrar_selecionar_gerar_em_massa.png)

Após filtrar, as cobranças correspondentes serão exibidas e você poderá **selecionar todas** para gerar as notas clicando em **Gerar (número de cobranças selecionadas) NFCom**.

> Como visto no tópico anterior, o cadastro do **Fulano da Silva** tem **produto personalizado**. A nota dele usará as **configurações do produto** definidas na ficha do assinante e a **porcentagem da base de cálculo** salva ali. Para os demais assinantes, sem personalização, valem os produtos e percentuais definidos em **NFCom → Configurações**.  
{.is-danger}

---

## Listagem de Notas

As notas são agrupadas por **competência**.  
Para visualizar, acesse **NFCom → Notas**:
<br>

![listagem_competencia1.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/listagem_competencia1.png)

Para ver as notas de uma **competência específica**, clique no botão de ação **Visualizar notas** na linha desejada:

![listagem_notas1.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/listagem_notas1.png)

---

## Impressão dos DANFE-COM em massa

Para imprimir os **DANFE-COM** das NFCom de uma competência:

1. Acesse a listagem de competências em **NFCom → Notas**.  
2. Clique no botão **Imprimir DANFEs** na competência desejada.

<br>

![imprimir_em_massa.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/imprimir_em_massa.png)

---

## Download dos XML das notas

Para baixar os **XML das notas em massa**:

1. Acesse a listagem de competências em **NFCom → Notas**.  
2. Clique no botão **Baixar XMLs** na competência desejada.  
3. Os arquivos serão baixados em um único arquivo **.zip** contendo os XML correspondentes.

<br>

![baixar_xmls_notas.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/baixar_xmls_notas.png)

## Cancelamento em massa de NFCom

Para cancelar várias NFCom de uma vez, siga os passos abaixo:

1. Acesse **NFCom → Notas**.
2. Selecione a **competência** em que estão as notas que deseja cancelar.
3. Marque, na listagem, as notas que deseja cancelar utilizando as caixas de seleção na primeira coluna.
4. No campo de ações em lote, selecione a opção **Cancelar**.
5. Clique no botão de **Executar** (ícone de play) para confirmar a ação.

![cancelar_em_massa.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/cancelar_em_massa.png)

> Ao cancelar em massa, serão enviados pedidos de cancelamento apenas para notas **Autorizadas** que estejam dentro do prazo e regras da **SEFAZ** do seu Estado.  
> Notas fora do prazo ou com pendências podem retornar como **Rejeitadas** e devem ser tratadas individualmente.
{.is-warning}


## Atualização em massa de NFCom

A função de **Atualizar em massa** é usada para forçar o reprocessamento de notas que:

- Foram **Rejeitadas**; ou  
- Estão com status de **Erro**;  

e que já tiveram algum ajuste realizado (por exemplo: correção de certificado, produtos, CFOP, dados do tomador ou configurações da NFCom, dados modificados dos assinantes).

Siga os passos:

1. Acesse **NFCom → Notas**.
2. Selecione a **competência** em que estão as notas que deseja atualizar.
3. Utilize os filtros, se necessário, para localizar apenas as notas com status **Rejeitada** ou **Erro**.
4. Marque, na listagem, as notas que deseja atualizar.
5. No campo de ações em lote, selecione **Atualizar**.
6. Clique no botão de **Executar** (ícone de play).

![atualizar_em_massa.png](https://atlaz.wiki/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/atualizar_em_massa.png)

Após a execução:

- As notas selecionadas terão o status alterado para **Aguardando transmissão**.
- O sistema irá reenviar essas notas para a SEFAZ utilizando as **configurações atualizadas**.

> Utilize a atualização em massa **apenas depois** de corrigir a causa do erro (dados do cliente, produto, CFOP, certificado, ambiente, etc.).  
> Caso o problema persista, as notas voltarão a ser rejeitadas ou marcarão erro.
{.is-warning}


## Como verificar o motivo de rejeição ou erro da NFCom

Quando uma NFCom aparece com status **Rejeitada** ou **Erro**, você pode consultar o motivo diretamente na tela de notas fiscais.

1. Acesse o menu **NFCom → Notas**.
2. Selecione a **competência** em que a nota foi emitida.
3. Localize a nota com status **Rejeitada** ou **Erro**.
4. No final da linha da nota, clique no ícone de **visualização** (olho).
<br>

![motivo.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/motivo.png)


Na parte inferior da tela serão exibidas as **Tentativas** de envio dessa nota, contendo:

- **Data** da tentativa  
- **Tipo** (Transmissão, Retorno etc.)  
- **Resposta** (mensagem da SEFAZ ou do validador do sistema)  
- Botão **Ver detalhes**

Ao clicar em **Ver detalhes**, será aberto um modal com:

- Aba **Requisição**: mostra o **XML enviado** para a SEFAZ.
- Aba **Resposta**:
  - Para notas **Rejeitadas**: mostra o **XML de retorno** com o código e a mensagem de rejeição da SEFAZ (ex.: CNPJ divergente, CFOP inválido, série incorreta etc.).
  - Para notas com **Erro**: exibe a mensagem de erro gerada **antes da transmissão**, normalmente relacionada a **falha de validação**, configuração incorreta ou problema técnico no envio.

> Utilize essas informações para identificar exatamente o que está incorreto (dados do emitente, certificado, CFOP, produtos, percentuais, ambiente, etc.), ajuste a configuração necessária e, após corrigir, use a opção de **Atualizar** ou **Atualizar em massa** para que a nota volte para **Aguardando transmissão** e seja reenviada corretamente.
{.is-warning}


## Status
Principais status exibidos:
- **Autorizada:** o sistema realizou a validação e a nota foi **transmitida e autorizada** pela SEFAZ do seu estado.  
- **Rejeitada:** a nota passou pela validação, mas foi **rejeitada** pela SEFAZ do seu estado.  
- **Aguardando transmissão:** o sistema está **validando** a nota e fará a transmissão em breve.  
- **Aguardando cancelamento:** o sistema está realizando o cancelamento. 
- **Cancelada:** nota **autorizada** que foi **cancelada** pelo provedor.  
- **Erro:** nota que **não passou** na validação.

![status_nfcom_1.png](/nota-fiscal/nfcom/nfcom-prod-v1/atualização-10-11-25/status_nfcom_1.png)

---

> **Orientações oficiais**  
> • A obrigatoriedade nacional está prevista para **01/11/2025**.  
> • Consulte o **Portal NFCom** do seu Estado e o site da **SEFAZ** para credenciamento, ambientes (homologação/produção) e manuais atualizados.  
{.is-info}

> Caso precise de orientação sobre a **NFCom**, **entre em contato com nosso [suporte](https://wa.me/5515981259678?text=Ol%C3%A1%2C%20preciso%20de%20ajuda%20com%20a%20NFCom!)**.  
> Atendimento: segunda a sexta, das 9h às 12h e das 14h às 18h, **exceto feriados nacionais**.  
{.is-info}

## Links úteis
- [AJUSTE SINIEF Nº 7, DE 7 DE ABRIL DE 2022](https://www.confaz.fazenda.gov.br/legislacao/ajustes/2022/AJ007_22)  
- [AJUSTE SINIEF Nº 34, DE 6 DE DEZEMBRO DE 2024](https://portalsped.fazenda.mg.gov.br/spedmg/nfcom/Legislacao/)  
- [Portal da Nota Fiscal Fatura de Serviço de Comunicação Eletrônica – SVRS](https://dfe-portal.svrs.rs.gov.br/Nfcom)  
- [NFCom – SP (SEFAZ/SP)](https://portal.fazenda.sp.gov.br/servicos/nfcom)
