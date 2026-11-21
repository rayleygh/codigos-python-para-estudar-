# codigos-python para estudar 
total_turistas = 0
turistas_menos_10 = 0

soma_turistas_20 = 0
qtd_praias_20 = 0

maior_distancia = 0
praia_mais_distante = "" 

while True:
  turistas = int(input("quantidade de turistas:"))
  
  if turistas < 0 :
    break
  
  nome_praia = input("nome da praia :")
  distancia = float(input("distancia da praia (km):"))
  
  #total de turistas 
  total_turistas += turistas 
  
  #praias com menos de 10 km 
  if distancia < 10:
    turistas_menos_10 +=turistas
    
  #praia mais distante 
  if distancia > maior_distancia :
      maior_distancia = distancia 
      praia_mais_distante = nome_praia
      
  #praias com mais de 20 km 
  if distancia > 20 :
    soma_turistas_20 += turistas
    qtd_praias_20 +=1
    
    #calculo da porcentagem 
    if total_turistas > 0:
      porcentagem = (turistas_menos_10 * 100) / total_turistas 
    else:
        porcentagem = 0
        
    #calculo da media 
    if qtd_praias_20>0:
      media = soma_turistas_20 / qtd_praias_20
    else:  # caso não haja praias com mais de 20 km:
        media = 0.0  # valor padrão caso não haja praias com mais de 20 km 
        
        print("\nRESULTADOS")
        print(f"Porcentagem de turistas em prais com menos de 10 km :{porcentagem:.2f}%")
        print(f"Praia mais distante: {praia_mais_distante}")
        print(f"Média de turistas nas praias com mais de 50 km: {media:.2f}")
