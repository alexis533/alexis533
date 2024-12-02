# Sistema de Gestión Documental

# Lista para almacenar los documentos
documentos = []

# Función para crear un documento
def crear_documento():
    titulo = input("Ingrese el título del documento: ")
    contenido = input("Ingrese el contenido del documento: ")
    documento = {
        "titulo": titulo,
        "contenido": contenido
    }
    documentos.append(documento)
    print("Documento creado con éxito.")

# Función para mostrar todos los documentos
def mostrar_documentos():
    if len(documentos) == 0:
        print("No hay documentos disponibles.")
    else:
        for i, documento in enumerate(documentos):
            print(f"Documento {i+1}:")
            print(f"Título: {documento['titulo']}")
            print(f"Contenido: {documento['contenido']}\n")

# Función para buscar un documento por título
def buscar_documento():
    titulo = input("Ingrese el título del documento a buscar: ")
    for documento in documentos:
        if documento["titulo"] == titulo:
            print(f"Título: {documento['titulo']}")
            print(f"Contenido: {documento['contenido']}\n")
            return
    print("Documento no encontrado.")

# Función para eliminar un documento por título
def eliminar_documento():
    titulo = input("Ingrese el título del documento a eliminar: ")
    for i, documento in enumerate(documentos):
        if documento["titulo"] == titulo:
            del documentos[i]
            print("Documento eliminado con éxito.")
            return
    print("Documento no encontrado.")

# Menú principal
while True:
    print("Sistema de Gestión Documental")
    print("1. Crear documento")
    print("2. Mostrar todos los documentos")
    print("3. Buscar documento")
    print("4. Eliminar documento")
    print("5. Salir")
    
    opcion = input("Ingrese una opción: ")
    
    if opcion == "1":
        crear_documento()
    elif opcion == "2":
        mostrar_documentos()
    elif opcion == "3":
        buscar_documento()
    elif opcion == "4":
        eliminar_documento()
    elif opcion == "5":
        print("Hasta luego.")
        break
    else:
        print("Opción inválida. Por favor, inténtelo de nuevo.")
