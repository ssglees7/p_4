# p_4
### Funciones
def ingresar_usuario():
    while True:
        user = input("Ingrese nombre de usuario: ")
        if user not in d:
            break
        else:
            print("Usuario ya existe. Intento otro.")
    while True:
        sex = input("Ingrese sexo: ")
        if sex == "M" or sex == "F":
            break
        else:
            print("Debe ingresar M o F solamente. Intente de nuevo.")
    while True:
        num = 0
        letra = 0
        passw = input("Ingrese contraseña: ")
        if len(passw) >= 8:
            if " " not in passw:
                for c in passw:
                    if c in "0123456789":
                        num+=1
                    if c in "abcdefghijklmnñopqrstuvwxyz":
                        letra+=1
                if num > 0 and letra > 0:
                    print("Contraseña valida.")
                    d[user] = [passw, sex]
                    print("Usuario ingresado con exito!!")
                else:
                    print("Contraseña no valida. Intente otra.")
            else:
                print("Contraseña no valida. Intente otra.")
        else:
            print("Contraseña no valida. Intente otra.")

def buscar_usuario(user):
    if user in d:
        print("El sexo del usuario es:", d[user][1], "y la contraseña es:", d[user][0])
    else:
        print("El usuario no se encuentra.")

def eliminar_usuario(user):
    if user in d:
        del d[user]
    else:
        print("No se pudo eliminar usuario!")

### principal
d={}
while True:
    print("MENU PRINCIPAL")
    print("1.- Ingresar usuario.")
    print("2.- Buscar usuario.")
    print("3.- Eliminar usuario.")
    print("4.- Salir.")
    op = input("Ingrese opción: ")
    if op == "4":
        print("Programa terminado...")
        break
    elif op == "1":
        ingresar_usuario()
    elif op == "2":
        usuario = input("Ingrese usuario a buscar: ")
        buscar_usuario(usuario)
    elif op == "3":
        usuario = input("Ingrese usuario a buscar: ")
        eliminar_usuario(usuario)
    else:
        print("Debe ingresar una opción válida!!")
        
