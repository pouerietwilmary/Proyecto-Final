# Proyecto-Final
Lidia Wilmary Poueriet Soliman 2020-10451

'''Tabla de amortizacion'''
import replit
def menu_principal():
  class resultados():
    monto=float(input("Ingrese el monto a prestar:\n"))
    cuotas=(int(input("Ingrese los plazos para pagar el monto de: "+str(monto)+"\n")))
    interes=(float(input("Ingrese ahora los intereses para pagar el monto\n")))
    replit.clear()
    interes=interes*0.01

    cuota_almacenada=monto*(((1+interes)**cuotas)*interes)

    cuota_almacenada=cuota_almacenada/(((1+interes)**cuotas)-1)

    saldo=monto
    
    cuota_almacenada="{0:.2f}".format(cuota_almacenada)
    print("\n\nResultado:\n")
    print("\nPeriodo:0| Cuota:0| Intereses:0| Abono:0| Saldo:{0}\n".format(saldo))

    for i in range (1,cuotas + 1):
      interes_operable="{0:.2f}".format(float(saldo)*float(interes))

      abono="{0:.2f}".format(float(cuota_almacenada)-float(interes_operable))

      saldo="{0:.2f}".format(float(saldo)-float(abono))
      if(float(saldo)<0):
        saldo="Completado"
      print("Periodo:{0}| Cuota:{1}| Intereses:{2}| Abono:{3}| Saldo:{4}\n".format(i,cuota_almacenada,interes_operable,abono,saldo))
menu_principal()
