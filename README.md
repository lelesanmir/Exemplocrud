# Exemplocrud
CRUD no banco de dados com php.


No contexto da programação orientada a objetos, explique o que é uma "interface". Como o que aparece no código do artigo: interface iDaoModeCrud { public function create( $object ); public function read( $param ); public function update( $object ); public function delete( $param ); }
class DaoContato implements iDaoModeCrud { ...

R - A classe "DaoContato" implementa a interface "iDaoModeCrud" e, portanto, deve fornecer uma implementação concreta para os métodos "create", "read", "update" e "delete". Ao fazer isso, a classe "DaoContato" se torna compatível com a interface "iDaoModeCrud" e pode ser usada onde quer que a interface seja exigida. Isso é útil em situações em que diferentes classes podem fornecer comportamentos diferentes, mas compatíveis, para uma interface comum.

O que são "traits" no PHP?
R - Traits no PHP são uma forma de reutilização de código que permite que as classes compartilhem métodos e propriedades comuns sem precisar herdar de uma classe base comum. Em outras palavras, um Trait é uma unidade de código que pode ser incorporada em uma classe para fornecer funcionalidade adicional sem afetar a hierarquia de herança existente.

Os Traits são semelhantes às classes abstratas em que ambos podem definir métodos e propriedades, mas os Traits não podem ser instanciados sozinhos. Em vez disso, eles são usados como um mecanismo de composição para adicionar comportamento a uma classe. Uma classe pode usar múltiplos Traits, e um Trait pode ser usado em múltiplas classes.

No código aparece o método "bindValue" do PDO para definir o valor que será utilizado na execução da instrução SQL. No PDO, também existe o método "bindParam". Qual(is) a(s) diferença(s) entre eles?
R - Tanto o método "bindValue" quanto o método "bindParam" do PDO são usados para definir valores que serão utilizados na execução de instruções SQL preparadas. No entanto, existem algumas diferenças importantes entre eles:

O método "bindValue" vincula um valor a um parâmetro de uma instrução preparada. Ou seja, o valor é avaliado imediatamente e o parâmetro recebe o valor resultante. Qualquer alteração posterior no valor original não afetará o valor atribuído ao parâmetro da instrução SQL.

Já o método "bindParam" vincula uma variável ao parâmetro de uma instrução preparada. Nesse caso, a variável é avaliada somente no momento da execução da instrução preparada, e qualquer alteração posterior no valor da variável é refletida no valor passado para a instrução preparada.

Além disso, a assinatura dos métodos também é diferente. O método "bindValue" recebe dois parâmetros: o primeiro é o nome ou posição do parâmetro na instrução SQL, e o segundo é o valor que será vinculado a ele. Já o método "bindParam" recebe três parâmetros: o primeiro é o nome ou posição do parâmetro na instrução SQL, o segundo é a variável que será vinculada a ele, e o terceiro é um opcional que especifica o tipo de dados que será vinculado ao parâmetro.

Em resumo, o método "bindValue" é mais adequado para valores simples que não precisam ser alterados posteriormente, enquanto o método "bindParam" é mais adequado para valores que precisam ser atualizados antes da execução da instrução SQL. No entanto, a escolha entre um método e outro depende do contexto específico em que estão sendo utilizados.

4 - No código é utilizada função "__autoload()" que foi descontinuada ("deprecated") no PHP desde a versão 7.2.0 e foi removida no PHP 8.0.0. Reescreva o código para efetuar o autoload de classes na versão atual do PHP.

R - Na versão atual do PHP (a partir da versão 7.4), recomenda-se utilizar o recurso "autoload" padrão do PHP, que é uma função anônima registrada usando a função "spl_autoload_register". Essa função permite que você registre uma ou mais funções para serem chamadas automaticamente pelo PHP sempre que uma classe não definida é instanciada.

Na tabela "contatos" a coluna "id" tem auto-incremento. Entretanto, o código implementado busca o próximo valor de "id" a ser inserido usando um "SELECT MAX(ID) AS ID FROM {$this->tabela}". Reescreva o método que faz INSERT para usar o recurso de auto-incremento do banco de dados.
R - Se a coluna "id" da tabela "contatos" está configurada com auto-incremento, não é necessário buscar o próximo valor de "id" a ser inserido manualmente. O próprio banco de dados se encarregará de gerar um novo valor de "id" automaticamente a cada nova linha inserida.

Dessa forma, o método de inserção pode ser simplificado para omitir a busca pelo próximo valor de "id". Aqui está um exemplo de como reescrever o método para utilizar o auto-incremento do banco de dados:

Implemente o código para criar as telas para que um usuário possa realizar as operações de consulta (select), inserção (insert), alteração (update) e exclusão (delete).
DICAS: Para testar o código: R - Foi o código feito.
