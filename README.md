import requests
from bs4 import BeautifulSoup as Soup
r = requests.get("https://www.nur.kz/food/recipes/1604632-beshbarmak-recept-klassicheskiy/")
s = Soup(r.text, "html.parser")
list = s.find_all(class_= "recipe-content__wrapper-block block-ingredients--with-border block-ingredients")

for x in list:
  p = x.find_all('a')
  for j in p: 
    print(j.text)
