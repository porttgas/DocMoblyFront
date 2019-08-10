Bob, filezilla, Salesforce, Chaordic, Heroku, git, testes

# Manual Front Moblys
## Observações iniciais:
Esse arquivo estará meio incompleto pois foi feito somente após a revogação ao meu acesso ao Bob. Esse arquivo poderá ir sendo atualizado conforme as necessidades.

## Como usar o Bob
### Para campanha principal (Desktop)
No menu superior, apertar no item Content. No icone da lupa, localizado na barra superior direita, buscar pelo bloco **Home-linha-1**. Esse bloco é dividido em dois campos geralmente: o **text** e **dynamic css**. No text, pegar o HTML e fazer as alterações, colocando os nomes certos para as imagens e os links. Os links estão na planilha, na coluna  *link homepage (desktop)* (No caso das campanhas principais)<br>
*PS:* Para campanhas principais, usar só o link do allproducts no banner<br>
### Para as apostas
No mesmo bloco da campanha principal, há o html das apostas. Ambos ficam no slider e elas aparecem, normalmente, depois das campanhas. Para facilitar, um código foi implementado no cronograma. Nas últimas colunas há blocos HTML e, ao lado, o nome da imagem que está sendo usada naquele bloco como background. <br>
**Passos**: colocar as imagens no servidor via ftp (no caso, filezilla (Mais sobre sua funcionalidade mais tarde)), copiar  o nome dos arquivos (incluindo a extenão (jpg, png, etc)), colar na coluna ao lado da que gera o HTML, copiar esse código produzido e colar na parte indicada no código parassssss as subcampanhas
### Subcampanhas:
Seguem mais ou menos o mesmo principio das apostas. Um código já está aplicado no cronograma que pode gerar o html da mesma forma.<br>
**Passos**: Colocar imagens no servidor via filezilla, copiar o nome do arquivo, colar o nome na coluna da aba e subcampanhas indicada para desktop, copiar o código gerado na planilha na parte e colar na parte indicada no bloco **home-linha-2** (Encontrado no mesmo processo da home-linha-1: buscar o nome na caixa de texto e acessá-las)