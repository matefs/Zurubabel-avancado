## Zurubabel avançado

- Ao ser registrado um novo banco de dados, automaticamente é criado dois arquivos:
    - .mdf = onde é armazenado os dados 
    - .ldf = log de onde fica armazenado o registro das transações.

- Ainda existe outro tipo de arquivos para armazenamento da dados:
    - ndf = arquivos secundários

- A organização dos registros é organizada conforme arquivos (filegroups )


###  Aula 10 - Armazenamento de Dados nas páginas
``` 

	Funções de verificação
		sys.dm_db_database_page_allocations
		dbcc ind

	# Os dados são armazenados em páginas
	# Cada página possui N linhas de dados
	# Os campos são:
	•	PageFID – O id do arquivo da página;
	•	PagePID – o número da página no arquivo;
	•	IAMFID – O id do arquivo IAM (Index Allocation Map) que mapeia esta página (se o arquivo foi um IAM, o resultado será nulo, assim como o IAMFID da primeira linha da m (https://technet.microsoft.com/pt-br/library/ms187501(v=sql.105).aspx)
	•	IAMPID – o número da página que o arquivo IAM mapeia esta página;
	•	ObjectId – O ID que o índice desta página faz parte;
	•	PartitionNumber – O número da partição que esta página está;
	•	PartitionID – O ID interno da página ao qual o datarow está alocado;
	•	Iam_chain_type – o tipo da unidade de alocação (IN_ROW_DATA (para tabelas HEAP), LOB_DATA (Large Object) e ROW_OVERFLOW_DATA);
	•	PageType – Representa o tipo da página. As mais comuns são:
		o	1  - página de dados;
		o	2 – página de índice;
		o	3 e 4 – páginas de texto;
		o	8 – páginas GAM;
		o	9 – páginas SGAM;
		o	10 – página IAM;
		o	11 – página PFS;
	•	IndexLevel – Em qual nível a página está do índice (isso se estiver em algum índice). O número vai desde o 0 (página folha – mais na borda da árvore) até a página N, que é a raiz;
	•	NextPagaFID e NextPagePID – Próximas páginas;
	•	PrevPageFID e PrevPagePID – Páginas anteriores de acordo com o índice;



```
