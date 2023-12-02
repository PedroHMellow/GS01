Henrique Rafael RM553945
Pedro Melo RM554223

O nosso projeto basicamente aborda o colesterol alto e o IMC alto das pessoas, onde criamos um programa que pede os dados do paciente, e o informa se seu IMC esta ideial ou se esta anormal, e o mesmo com o percentual de gordura, e com isso dependendo dos resultados ele indica para o paciente profissionais que podem o ajudar de uma forma melhor.
Ou seja nosso projeto é focado no monitoramento remoto paras os pacientes.

CODIGO FONTE 


def obter_dados_pessoais():
    while True:
        nome = input("Diga seu nome por gentileza: ")
        if nome:
            break
        else:
            print("Por favor, insira um nome válido.")

    while True:
        sx = input("Informe seu sexo, M para masculino e F para feminino: ").upper()
        if sx == "M" or sx == "F":
            break
        else:
            print("Por favor, insira M para masculino ou F para feminino.")

    if sx == "M":
        print("Você é do sexo masculino.")
    elif sx == "F":
        print("Você é do sexo feminino.")

    imc = None
    while imc is None:
        imc_str = input("Diga seu IMC por gentileza. Se não souber, calcule e nos informe: ")
        if imc_str.replace('.', '', 1).isdigit():
            imc = float(imc_str)
        else:
            print("Por favor, insira um valor numérico para o IMC.")

    gordura = None
    while gordura is None:
        gordura_str = input("Diga seu percentual de gordura por gentileza: ")
        if gordura_str.isdigit():
            gordura = int(gordura_str)
        else:
            print("Por favor, insira um valor numérico para o percentual de gordura.")

    while True:
        atividade_fisica = input("Você pratica alguma atividade física? SIM ou NAO: ").upper()
        if atividade_fisica == "SIM" or atividade_fisica == "NAO":
            break
        else:
            print("Por favor, responda com SIM ou NAO.")

    return nome, sx, imc, gordura, atividade_fisica

def analisar_dados_pessoais(nome, sx, imc, gordura):
    if imc < 18.5:
        print(f"{nome}, voce voce estaabaixo do peso")
    elif 18.5 <= imc <= 24.9:
        print(f"{nome},voce esta com o peso normal")
    elif 25 <= imc <= 29.9:
        print(f"{nome},voce esta sobrepeso")
    else:
        print(f"{nome},voce esta com obesidade. Consulte este artigo para mais informações sobre obesidade:https://www.cnnbrasil.com.br/saude/imc-o-bom-o-ruim-e-o-errado-na-hora-de-medir-o-indice-de-massa-corporal/")

    if gordura < 6:
        print(f"{nome}, o seu percentual de gordura esta muito baixo")
    elif 6 <= gordura <= 24 and gordura <= 30:
        print(f"{nome}, o seu percentual de gordura esta essencial ou aceitável")
    elif 25 <= gordura <= 31 and gordura <= 36:
        print(f"{nome},o seu percentual de gordura é aceitável ou sobrepeso")
    else:
        print(f"{nome}, percentual de gordura no intervalo de sobrepeso. Consulte este artigo para mais informações sobre sobrepeso: https://guilhermegiorelli.blogosfera.uol.com.br/2018/07/28/o-que-e-falsa-magra-quando-o-problema-e-percentual-de-gordura-e-nao-peso/")
        print(f"{nome} , caso não pratique atividade física, consulte este site que mostram os riscos da fala de ativida física: https://news.un.org/pt/story/2022/10/1804027 ")

nome_usuario, sexo_usuario, imc_usuario, gordura_usuario, atividade_fisica_usuario = obter_dados_pessoais()


analisar_dados_pessoais(nome_usuario, sexo_usuario, imc_usuario, gordura_usuario)

print("Caso tenha problemas mais sérios entre em contato com nosco NotreDame Labs: https://www.hapvida.com.br/site/noticias/seja-bem-vindoa-%C3%A0-hapvida-notredame-interm%C3%A9dica ")





