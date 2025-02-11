O parâmetro --rm no comando:

bash
Copiar
Editar
docker run -it --rm python:3.13 bash
faz com que o container seja automaticamente removido assim que ele for encerrado.

🛠️ Explicação dos parâmetros:
docker run → Cria e executa um novo container.
-it → Torna o terminal interativo (-i mantém a entrada aberta, -t aloca um terminal).
--rm → Remove o container automaticamente ao sair.
python:3.13 → Usa a imagem oficial do Python 3.13.
bash → Executa o shell Bash dentro do container.
✅ Vantagens do --rm
Evita o acúmulo de containers parados no sistema.
Mantém o ambiente limpo, sem a necessidade de remover containers manualmente.
❌ Desvantagem
O container e todas as alterações feitas dentro dele serão perdidas quando ele for encerrado. Se precisar manter dados, use volumes ou crie um container persistente.
Se quiser um container que continue existindo após ser parado, remova o --rm e rode:

bash
Copiar
Editar
docker run -it --name meu_container python:3.13 bash
Depois, ele pode ser reiniciado com:

bash
Copiar
Editar
docker start -ai meu_container
