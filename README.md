# Hora-AM-PM
Conversor de horario para AM e PM



horas = []
minutos = []
g = True # Variavel para estracao de simbolos indesejados.
am = "AM"
pm = "PM"
#f = ""

        
def hora(x, y):
      global fuso, br
      
      h = int(input("Informe o ponteiro da hora: ")) 
      
      while h > 24 or h < 1: # so aceita o h com valor de 1 a 24 , corespondendo as 24 horas.
            print("Hora inccorrta: ")
            h = int(input("Informe o ponteiro da hora: "))
            
      m = int(input("Informe o ponteiro do minuto: "))
      while 60 < m > 1: # so aceite o m de 1 a 60 correnpondendo os 60 minutos.
            print("Informacao Incorreta.")
            m = int(input("Informe o ponteiro do minuto: "))
            
      #Formala convertendo o horario para AM ou PM
      if h == 12:
            h = 12
            horas.append(h)
            minutos.append(m)
            fuso = pm

      elif h == 24:
            h -= 12
            horas.append(h)
            minutos.append(m)
            fuso = am
            
      elif h > 12:
            h -= 12
            horas.append(h)
            minutos.append(m)
            fuso = pm
            
      elif h < 12:
           h = h
           horas.append(h)
           minutos.append(m)
           fuso = am
           
      return horas, minutos, fuso

a = list(hora(horas ,minutos)) # a transforma a funcao hora em uma lista.
b = str(a) # b recebe o ultimo valor de hora e de minutos que foram coletados pela variavel (a).


if g: # usando variaveis para retirar todos os simbolos coletados nas variaveis anteriores, permanecendo somente com numeros, e fuso.
      c = b.replace("[", "")
if g:
      d = c.replace("]", "")
if g:
      e = d.replace(",", "")

def imprime():
      global horas

      if fuso == am and horas[0] <= 10:
            print("%s%s:%s %s"%(e[0],e[1],minutos[0],fuso))
      elif fuso == am and horas[0] >= 10:
            print("%s%s:%s %s"%(e[0],e[1],minutos[0],fuso))
      elif fuso == "PM" and horas[0] == 12:
            print("%s%s:%s %s"%(e[0],e[1],minutos[0],fuso))
      elif fuso == pm and horas[0] >= 10:
            print("%s%s:%s %s"%(e[0],e[1],minutos[0],fuso))
      elif fuso == pm:
            print("%s:%s %s"%(e[0],minutos[0],fuso))
      
imprime()

