# Cotacao-dolar-atualizado
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
#abrir o navegador
navegador = webdriver.Chrome()
#abrir o google do navegador
navegador.get("Https://www.Google.com/")
#selecionar e escrever a barra de pesquisa do navegador e dar enter
navegador.find_element('xpath', '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').send_keys("cotação dolar")
navegador.find_element('xpath', '/html/body/div[1]/div[3]/form/div[1]/div[1]/div[1]/div/div[2]/input').send_keys(Keys.ENTER)
cotacao_dolar = float( navegador.find_element('xpath', '//*[@id="knowledge-currency__updatable-data-column"]/div[1]/div[2]/span[1]').get_attribute('data-value'))
#saida
print(f"""O dolar está {cotacao_dolar:,.2f}""")
navegador.quit()
real = float (input("Você tem quantos reais?"))
dolar = real/cotacao_dolar
print(f"""Você terá {dolar:,.2f} dolares.""")
