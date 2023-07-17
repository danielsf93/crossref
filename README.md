# crossref


Modificação do plugin de exportação de xml da crossref a pedido da Agência de Bibliotecas e Coleções Digitais da Universidade de São Paulo<br><br>
A modificação tem por objetivo gerar arquivo xml que contenha os DOI's da página do artigo, do arquivo em português e dos arquivos traduzidos.<br> <br>
<i>Se o artigo tiver 1 pdf apenas, o plugin vai funcionar como de padrão, gerando XML com DOI somente para a página do artigo. Se tiver de 2 pdf's adiante vai pegar o DOI (galleyDoi) de cada um e adicionar no arquivo XML com a tag <journal_article>. Por enquanto funciona para artigos que possuam até no máximo 10 PDF's. Acredito que não seja necessário uma capacidade maior, pois a maioria de artigos que possuem traduções, rondam o número de 3 PDF's<br></i>
<br>
<b>Modificações principais:</b><br>
plugins/importexport/crossref/filter/ArticleCrossrefXmlFilter.inc.php<br>
<br>
-Modificações:
-function createJournalNode<br>
-function createJournalArticleNode01<br>
-(...)<br>
-function createJournalArticleNode10<br>
Obs: Funciona até o infinito, mas como dito anteriormente, limitei até 10 PDF's<br>
-function createJournalArticleNode ∞ <br><br>

<b>Exemplos</b><br>
A pasta "testes xml" possui arquivos xml produzidos por este plugin<br><br>
<b>Observações:</b><br>

-Verificar para onde deve apontar o DOI dos pdf's, por enquanto aponta para o link de download. É possível modificar para link de view.<br>
-Verificar quantas mais funções de "createJournalArticleNodexxxx" serão necessárias para suprir a necessidade da USP.<br>
-Verificar se todas as subtags da tag <journal_article> são realmente necessárias, pois retornam links dos outros arquivos, titulo, resumo, etc...<br>

