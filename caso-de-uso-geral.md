@startuml
left to right direction

skinparam packageStyle rectangle

actor Administrador
actor Vendedor
actor "Funcionário de Estoque" as FuncEstoque

rectangle "Sistema Bravos Fightwear" {

    ' Produtos
    usecase "Cadastrar produto" as UC01
    usecase "Editar produto" as UC02
    usecase "Excluir produto" as UC03
    usecase "Consultar produto" as UC04

    ' Categorias
    usecase "Gerenciar categorias" as UC05

    ' Clientes
    usecase "Cadastrar cliente" as UC06
    usecase "Editar cliente" as UC07
    usecase "Excluir cliente" as UC08
    usecase "Consultar cliente" as UC09
    usecase "Consultar histórico de compras" as UC10

    ' Fornecedores
    usecase "Cadastrar fornecedor" as UC11
    usecase "Editar fornecedor" as UC12
    usecase "Excluir fornecedor" as UC13
    usecase "Consultar fornecedor" as UC14

    ' Estoque
    usecase "Gerenciar estoque" as UC15
    usecase "Registrar entrada" as UC16
    usecase "Registrar saída" as UC17
    usecase "Ajustar estoque" as UC18
    usecase "Consultar estoque baixo" as UC19

    ' Vendas
    usecase "Registrar venda" as UC20
    usecase "Adicionar produtos à venda" as UC21
    usecase "Calcular total da venda" as UC22
    usecase "Atualizar estoque" as UC23

    ' Pagamentos
    usecase "Registrar pagamento" as UC24
    usecase "Consultar pagamento" as UC25

    ' Funcionários
    usecase "Cadastrar funcionário" as UC26
    usecase "Editar funcionário" as UC27
    usecase "Consultar funcionário" as UC28
    usecase "Definir permissões" as UC29

    ' Dashboard
    usecase "Visualizar dashboard" as UC30

    ' Relatórios
    usecase "Consultar relatórios" as UC31
    usecase "Filtrar por período" as UC32

    ' Autenticação
    usecase "Realizar login" as UC33
    usecase "Controlar permissões" as UC34
}

' ==========================
' ADMINISTRADOR
' ==========================

Administrador --> UC33

Administrador --> UC01
Administrador --> UC02
Administrador --> UC03
Administrador --> UC04

Administrador --> UC05

Administrador --> UC06
Administrador --> UC07
Administrador --> UC08
Administrador --> UC09
Administrador --> UC10

Administrador --> UC11
Administrador --> UC12
Administrador --> UC13
Administrador --> UC14

Administrador --> UC15
Administrador --> UC19

Administrador --> UC26
Administrador --> UC27
Administrador --> UC28
Administrador --> UC29

Administrador --> UC30
Administrador --> UC31

' ==========================
' VENDEDOR
' ==========================

Vendedor --> UC33

Vendedor --> UC04
Vendedor --> UC06
Vendedor --> UC07
Vendedor --> UC09
Vendedor --> UC10

Vendedor --> UC20
Vendedor --> UC24
Vendedor --> UC25

' ==========================
' FUNCIONÁRIO DE ESTOQUE
' ==========================

FuncEstoque --> UC33

FuncEstoque --> UC04

FuncEstoque --> UC15
FuncEstoque --> UC16
FuncEstoque --> UC17
FuncEstoque --> UC18
FuncEstoque --> UC19

' ==========================
' RELACIONAMENTOS
' ==========================

UC20 ..> UC21 : <<include>>
UC20 ..> UC22 : <<include>>
UC20 ..> UC23 : <<include>>
UC20 ..> UC24 : <<include>>

UC31 ..> UC32 : <<extend>>

UC33 ..> UC34 : <<include>>

@enduml
