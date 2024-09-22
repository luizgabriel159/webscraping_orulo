from selenium import webdriver
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.common.keys import Keys
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
import time

chrome_options = Options()
#chrome_options.add_argument("--headless")  # Para rodar sem abrir o navegador
chrome_options.add_argument("--no-sandbox")
chrome_options.add_argument("--disable-dev-shm-usage")
service = Service(executable_path=r"C:\Users\"ocultado por questão de privacidade"\Downloads\chromedriver-win64\chromedriver-win64\chromedriver.exe")
driver = webdriver.Chrome(service=service, options=chrome_options)

#Acessando o site
driver.get("https://auth.orulo.com.br/email?client_id=TKYZFTALAu1tshVidMJdV15BKz97ghBs_xaoarFpCiY&return_to=https%3A%2F%2Fwww.orulo.com.br%2Foauth%2Fauthorize%3Fclient_id%3DTKYZFTALAu1tshVidMJdV15BKz97ghBs_xaoarFpCiY%26redirect_uri%3Dhttps%253A%252F%252Fwww.orulo.com.br%252Fcustomers%252Foauth2%252Fcallback%26response_type%3Dcode&_gl=1*myzrm3*_gcl_au*MTc4ODA0MjEzOC4xNzI1NDkyNDM2")


username = WebDriverWait(driver, 10).until(
EC.presence_of_element_located((By.ID, "email"))  
)
password = driver.find_element(By.ID, "password")  

#Logando...
username.send_keys("ocultado por questão de privacidade")  
password.send_keys("ocultado por questão de privacidade")  
password.send_keys(Keys.RETURN)


WebDriverWait(driver, 10).until(
    EC.presence_of_element_located((By.CLASS_NAME, "Fazer login"))
)
print("Login realizado com sucesso!")


#O resto do código foi ocultado por questão de ética, o código completo em teoria é propriedade da empresa...



