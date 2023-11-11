# Mybank
#ingreso de datos y validación
#Ingreso de datos
print("--------------BIENVENID@ A MI BANCO--------------")
#Documento del usuario:
while True:
    try:
      documento =  input("Ingrese el número del documento: ")
      if len(documento) == 10:
          resultado = float(documento)
          break
      else:
          print("Digite un documento válido")
    except:
        print("Digite un documento válido")
#Nombre usuario:
nombre = input("Ingrese el nombre del cliente: ").title()
#Válidación del tipo de cuenta:
while True:
    try:
     tipo_cuenta = str(input("Digite su tipo de cuenta: Ahorro, CDT, Corriente: ")).upper().strip()
     if tipo_cuenta in ["CDT", "CORRIENTE"]:
            exo = "- Exonerado del 4*1000"
            break
     elif tipo_cuenta == "AHORRO":
         exo = ""
         break
     else:
         print("Digite un tipo de cuenta válido")
         continue
    except ValueError:
        print("Digite un tipo de cuenta válido")
#Validación de consignación:   
while True:
    try:
        consignacion = float(input("Ingrese el valor a cosignar: ")) 
        if consignacion > 0:
            match consignacion:     
                case consignacion   if consignacion > 1000000:
                            bono = "- Bono navideño"
                            break
                case consignacion if consignacion >= 500000 and consignacion <= 1000000:
                            bono = "- Participa en rifa"
                            break
                case consignacion if consignacion < 5000000:
                    bono = ""   
                    break
                case _:
                    print("No se identificó el valor") 
                    continue  
        else:
            print("Error: Digite un valor válido") 
    except:
        print("Error: Digite un valor válido")       
#Consultas
print("\n----------------------CONSULTA DE DATOS DEL CLIENTE---------------------")
print("DOCUMENTO         :{}".format(documento))
print("CLIENTE           :"+nombre)
print(f"CUENTA            :{tipo_cuenta} {exo} ")
print("CONSIGNACION      :${:,.0F}  {}".format(consignacion, bono,))
