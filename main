import requests
from bs4 import BeautifulSoup

def getLinks(url, l):
  urls = []
  urls2 = []
  urls3 = []
  
  try: reqs = requests.get(url)
  except: reqs = requests.get(url, verify = False)
  soup = BeautifulSoup(reqs.text, 'html.parser')
   
  for link in soup.find_all('a'): # get links
    urls.append(link.get('href'))
    
  for i in range(len(urls)): # parse links
    try:
      if urls[i][0:5] == 'https':
        urls2.append(urls[i])
    except: pass
  
  for links in urls2: # remove duplicates/ parse by domain
    c = 0
    for i in range(len(links)):
      if links[i] == '/':
        if c == 2:
          if not(links[0:i] in urls3 or links[0:i] in l):
            urls3.append(links[0:i])
          c += 1
        else: c += 1
  print(len(urls3),'links found from domain',url) # link printing
  return urls3

def botIndex():
  i = int(open('i.txt','r').read())
  while True:
    data = open('index.txt','r').read()
    if data.split('\n')[len(data.split('\n'))-1] == '':
      with open('index.txt','w') as f: f.write(data[:-1])

    try:
      links = open('index.txt','r').read().split('\n')
      with open('index.txt','a') as file:
        l = getLinks(links[i], links)
        if not(links == []):
          file.write('\n'+'\n'.join(l))
    except: pass
    i += 1
    with open('i.txt','w') as file:
      file.write(str(i))   

if __name__ == '__main__':
  botIndex()
