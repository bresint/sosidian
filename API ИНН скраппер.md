#upgrade #myScript #screpper #apikeys
# Code
```
import requests 
 
F = open("/home/mcc/code/puthon files(examples)/inn base", "r") #file with INNlist
f = open("/home/mcc/code/puthon files(examples)/file", "w") # file with JSON database
BaseIPUrl = "http://suggestions.dadata.ru/suggestions/api/4_1/rs/findById/party"
key = "b21d9e6d285cd14a75347d4b4ade639196ff2193"
Lines = F.read().splitlines() 

for i in Lines:
innObj = {"query": i}
Headers = {"Content-Type": "application/json","Accept": "application/json", "Authorization": "Token "+key} #!everu API request need headers, theyre not universal

x = requests.post(BaseIPUrl, headers = Headers, json = innObj)

f.write(x.text)
```
# информация о программе
**api** сайта dadata.ru для скраппинга, сайт платный по большей части, бесплатный доступ по почте(ограниченное количество запросов)
**key** b21d9e6d285cd14a75347d4b4ade639196ff2193
выдает информацию в формате json
**Необходимо улучшить**: в идеале забить в переменные все возможные headers доступные с этого сайта, а так же научиться/автоматизировать работу с Json


