# coding : utf-8 
#faire dérouler le code HTML de la page d'accueil de l'hebdo : l'oeil régional 

from bs4 import BeautifulSoup 
import requests

source = requests.get('https://www.oeilregional.com/').text

soup = BeautifulSoup(source, 'lxml')

print(soup.prettify())

#faire ensuite dérouler dans le terminal les urls des articles écrits par les journalistes de l'oeil régional dernièrement. 

import csv 
import requests 
from bs4 import BeautifulSoup

fichier = "loeil_regional.csv"

urlDebut = "https://www.oeilregional.com/?p="

url = "https://www.oeilregional.com/?p=20801"

nombres = list(range(20000,20900))

entetes = {"User-Agent" : "Catherine Savoie - requête acheminée dans le cadre d'un cours de journalisme de données",
"From":"savoiesoccer@hotmail.com" 
}

for nombre in nombres: 
    urlarticle = urlDebut + str(nombre)
    contenu = requests.get(urlarticle,headers=entetes)

print(page)

#trouver le  nom de l'auteur du texte "LDT et les Chiefs à une victoire du Super Bowl"

fichier = "loeil_regional.csv"

url = "https://www.oeilregional.com/ldt-et-les-chiefs-a-une-victoire-du-super-bowl/"

entetes = {"User-Agent" : "Catherine Savoie - requête acheminée dans le cadre d'un cours de journalisme de données",
"From":"savoiesoccer@hotmail.com" 
}

contenu = requests.get(url, headers=entetes)

page = BeautifulSoup(contenu.text, "htmlparser")

print(page.find("div", class_="name")).a.text 
