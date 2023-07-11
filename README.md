# crossref


Modificação do plugin de exportação de xml da crossref a pedido da Agência de Bibliotecas e Coleções Digitais da Universidade de São Paulo<br><br>
A modificação tem por objetivo gerar arquivo xml que contenha os DOI's da página do artigo, do arquivo em português e do arquivo traduzido.<br> <br>
<i>Por enquanto só funciona se o artigo possuir 2 pdf's. Se o artigo tiver 1 pdf apenas, o plugin vai funcionar como veio funcionando até aqui. Se tiver 2 pdf's vai pegar o doi (galleyDoi) de cada um e adicionar no arquivo xml com a tag <journal_article><br></i>
<br>
<b>Modificações principais:</b><br>
plugins/importexport/crossref/filter/ArticleCrossrefXmlFilter.inc.php<br>
<br>
-Modificação 01:<br>
contando o número de pdf's para chamar as funções<br>
	 -createJournalArticleNodedois<br>
	 -createJournalArticleNodetres<br><br>
  
-Modificação 02:<br>
-createJournalArticleNodedois<br>
Vai verificar qual é o primeiro pdf e seu DOI respectivo. Preenche os correspondentes das subtags <doi> e <resource>
A parte modificada do código aparece logo em seguida com "modificação 02 INICIO / FIM"<br><br>

-Modificação 03:<br>
-createJournalArticleNodedois<br>
Vai verificar qual é o segundo pdf e seu DOI respectivo. Preenche os correspondentes das subtags <doi> e <resource>
A parte modificada do código aparece logo em seguida com "modificação 03 INICIO / FIM"<br><br>

#Exemplos
A pasta "testes xml" possui arquivos xml produzidos por este plugin

#Observações:

-Verificar para onde deve apontar o DOI dos pdf's, por enquanto aponta para o link de download. É possível modificar para link de view.<br>
-Verificar quantas mais funções de "createJournalArticleNodexxxx" serão necessárias para suprir a necessidade da USP.<br>
-Verificar se todas as subtags da tag <journal_article> são realmente necessárias, pois retornam links dos outros arquivos, titulo, resumo, etc...<br>
-Verificar se a regra de DOI's para arquivos também deve ser implementada para artigos que só possuem 1 pdf.
