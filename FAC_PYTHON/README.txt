Instruções de Uso do Aplicativo 

1. Imagem de Fundo:
   - O aplicativo utiliza uma imagem de fundo para decorar a interface.
   - A imagem de fundo atual é "catimage.png". Para substituí-la por outra imagem, siga estas etapas:
      a. Selecione a imagem desejada para substituir a "catimage.png".
      b. Renomeie sua nova imagem para "catimage.png".
      c. Certifique-se de que a nova imagem esteja no mesmo diretório que o script Python do aplicativo.
      d. Execute o aplicativo novamente para ver a nova imagem de fundo.

2. Execução do Aplicativo:
   - Para executar o aplicativo, basta executar o script Python que no caso é " teste.py  " no seu ambiente Python.



3. Interagindo com o Aplicativo:
   - O aplicativo exibe campos para inserir informações como nome, estado e CPF.
   - Insira os dados nos campos correspondentes e clique no botão "Salvar" para salvar as informações.
   - Clique no botão "Quit" para fechar o aplicativo.


regras 

#começar com tela com um botão e um entry (nome)- v1  OKAY 

#adicionar mais duas entrys (cpf e estado) e suas labels - v2  OKAY 

 #mudar o fundo para uma imagem mais bonita, adicionar readme.txt explicando como usar - v3

#adicionar clicar no botão salva os 3 dados em um sqlite - v4

#Criar uma branch em que le um config.txt com uma lista de 5 estados possiveis separados por pular linha - x1
#Mudar o separador para ; e adicionar mais 5 estados - x2
#Voltar para main, criar outra branch e criar um dropdown com 3 opções (clt, mei, socio) - y1
#Voltar para main, Corrigir o bug da função de cpf - v5
#Merge de x com v - v6
#Adicionar verificação de CPF e de estado, com base na função cpf e na lista de estados .txt antes de adicionar no sqlite v7


### ### cuidado CUIDADOOOOO
cursor.execute("CREATE TABLE IF NOT EXISTS Tabela1 (nome TEXT, curso TEXT, matricula INTEGER)")
def VerificarCPF(CPF):
    #CPF deve ser na forma "123.456.789-10"
    for trecho in CPF.split("."):
        if len(trecho)!=3:
            return False
        else:
            return True

def inserevalores(Valor1, Valor2):
    #Insere linha na tabela
    cursor.execute("INSERT INTO Tabela1 VALUES ('"+Valor1+"', '"+Valor2+"')")

def pegavalores():
    #Pega valores da tabela
    rows = cursor.execute("SELECT * FROM Tabela1").fetchall()
    print(rows)
