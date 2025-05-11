# BIG-DATA

## Insercion de datos en mongodb
[
  {
    "_id": "a1b2c3d4-5678-1234-9876-abcdef123456",
    "title": "Jogger Hombre Azul Marino con Rayas",
    "brand": "Adreno",
    "category": "Ropa y Accesorios",
    "sub_category": "Ropa Inferior",
    "description": "Jogger cómodo de ajuste atlético, ideal para deporte o uso diario.",
    "url": "https://www.ejemplo.com/adreno-jogger-hombre-azul-marino",
    "pid": "ADRNZJ9EHFCY1A3X",
    "seller": "Distribuciones Globales",
    "actual_price": 2499,
    "selling_price": 849,
    "discount": "66% de descuento",
    "average_rating": 4.1,
    "out_of_stock": false,
    "images": [
      "https://example.com/img1_adreno.jpg",
      "https://example.com/img2_adreno.jpg"
    ],
    "crawled_at": "2021-10-02T20:11:53Z"
  },
  {
    "_id": "c9d8e7f6-4321-5678-9988-112233445566",
    "title": "Jeans Mujer Negro Entallado",
    "brand": "Denim&Co",
    "category": "Ropa y Accesorios",
    "sub_category": "Ropa Inferior",
    "description": "Jeans ajustados de mezclilla elástica, perfectos para uso diario.",
    "url": "https://www.ejemplo.com/denimco-jeans-mujer-negro",
    "pid": "DNMWNJ9EHFCY8Z5Q",
    "seller": "Moda Urbana S.A.S",
    "actual_price": 3199,
    "selling_price": 999,
    "discount": "69% de descuento",
    "average_rating": 4.3,
    "out_of_stock": false,
    "images": [
      "https://example.com/img1_denim.jpg",
      "https://example.com/img2_denim.jpg"
    ],
    "crawled_at": "2021-10-02T20:11:54Z"
  },
  {
    "_id": "d2f4g6h8-1357-2468-aaaa-bbccddeeff11",
    "title": "Camiseta Deportiva Hombre Roja",
    "brand": "SportMax",
    "category": "Ropa y Accesorios",
    "sub_category": "Parte Superior",
    "description": "Camiseta ligera y transpirable, ideal para entrenamientos intensos.",
    "url": "https://www.ejemplo.com/sportmax-camiseta-roja",
    "pid": "SPMXTJ9EHFCY2G7L",
    "seller": "Deportes Colombia",
    "actual_price": 1799,
    "selling_price": 699,
    "discount": "61% de descuento",
    "average_rating": 4.0,
    "out_of_stock": false,
    "images": [
      "https://example.com/img1_sportmax.jpg",
      "https://example.com/img2_sportmax.jpg"
    ],
    "crawled_at": "2021-10-02T20:11:55Z"
  },
  {
    "_id": "f1e2d3c4-9999-0000-7777-aabbccddeeff",
    "title": "Blusa Manga Larga Mujer Estampada",
    "brand": "FashionStyle",
    "category": "Ropa y Accesorios",
    "sub_category": "Parte Superior",
    "description": "Blusa moderna con estampado floral y tela suave al tacto.",
    "url": "https://www.ejemplo.com/fashionstyle-blusa-mujer",
    "pid": "FSHNBJ9EHFCY3M2D",
    "seller": "Tendencias Latinas",
    "actual_price": 2699,
    "selling_price": 899,
    "discount": "67% de descuento",
    "average_rating": 4.4,
    "out_of_stock": false,
    "images": [
      "https://example.com/img1_blusa.jpg",
      "https://example.com/img2_blusa.jpg"
    ],
    "crawled_at": "2021-10-02T20:11:56Z"
  },
  {
    "_id": "aabbccdd-1234-5678-9999-ffeeddccbbaa",
    "title": "Pantalón Deportivo Hombre Gris Oscuro",
    "brand": "ActiveWear",
    "category": "Ropa y Accesorios",
    "sub_category": "Ropa Inferior",
    "description": "Pantalón deportivo de algodón con cintura ajustable y bolsillos laterales.",
    "url": "https://www.ejemplo.com/activewear-pantalon-gris",
    "pid": "ACTWVJ9EHFCY4K9B",
    "seller": "RopaFit",
    "actual_price": 2299,
    "selling_price": 799,
    "discount": "65% de descuento",
    "average_rating": 3.8,
    "out_of_stock": false,
    "images": [
      "https://example.com/img1_active.jpg",
      "https://example.com/img2_active.jpg"
    ],
    "crawled_at": "2021-10-02T20:11:57Z"
  }
]

## Editar o actualizar campos

comercio_electrónico> db.Comercio.updateOne(
...   { _id: "a1b2c3d4-5678-1234-9876-abcdef123456" },
...   {
...     $set: {
...       selling_price: 799,   // Nuevo valor para el campo "selling_price"
...       discount: "70% de descuento"  // Nuevo valor para el campo "discount"
...     }
...   })
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
comercio_electrónico> db.Comercio.find({ _id: "a1b2c3d4-5678-1234-9876-abcdef123456" }).pretty()
[
  {
    _id: 'a1b2c3d4-5678-1234-9876-abcdef123456',
    title: 'Jogger Hombre Azul Marino con Rayas',
    brand: 'Adreno',
    category: 'Ropa y Accesorios',
    sub_category: 'Ropa Inferior',
    description: 'Jogger cómodo de ajuste atlético, ideal para deporte o uso diario.',
    url: 'https://www.ejemplo.com/adreno-jogger-hombre-azul-marino',
    pid: 'ADRNZJ9EHFCY1A3X',
    seller: 'Distribuciones Globales',
    actual_price: 2499,
    selling_price: 799,
    discount: '70% de descuento',
    average_rating: 4.1,
    out_of_stock: false,
    images: [
      'https://example.com/img1_adreno.jpg',
      'https://example.com/img2_adreno.jpg'
    ],
    crawled_at: '2021-10-02T20:11:53Z'
  }
]


33Eliminación  

db.Comercio.deleteOne({ _id: "a1b2c3d4-5678-1234-9876-abcdef123456" })



##  Consulta con filtros

db.Comercio.find({ category: "Ropa y Accesorios" })


##  Consulta con operadores

db.Comercio.find({ actual_price: { $eq: 2499 } })


## Contar número total de documentos en la colección

db.Comercio.aggregate([{ $count: "totalProductos" }])


##  Esto sumará todos los valores del campo selling_price en todos los documentos de la colección.

db.Comercio.aggregate([ { $group: { _id: null, totalVentas: { $sum: "$selling_price" } } } ])

----------------------------------------------------------------------------------------------
## Insertar datos en Apache HBase

import happybase
import pandas as pd
import os

try:

 # 1. Establecer conexión con Hbase

    connection = happybase.Connection('localhost')
    print("Conexión establecida con HBase")

# 2. Descargar el archivo si no existe localmente

    file_name = 'Trafico_Portuario_Maritimo_En_Colombia.csv'
    if not os.path.exists(file_name):
        import subprocess
        print("Descargando archivo...")
        url = 'https://www.datos.gov.co/api/views/5r3g-zv5z/rows.csv?accessType=DOWNLOAD'
        subprocess.run(['wget', '-O', file_name, url])

# 3. Crear la tabla con familias de columnas

    table_name = 'trafico_portuario'
    families = {
        'ubicacion': dict(),
        'operacion': dict(),
        'movimiento': dict(),
        'vigencia': dict()
    }

    if table_name.encode() in connection.tables():
        print(f"Eliminando tabla existente - {table_name}")
        connection.delete_table(table_name, disable=True)

    connection.create_table(table_name, families)
    table = connection.table(table_name)
    print("Tabla 'trafico_portuario' creada exitosamente")

 # 4. Cargar datos del CSV

   df = pd.read_csv(file_name)
    df.columns = df.columns.str.strip()

   for index, row in df.iterrows():
        row_key = f'puerto_{index}'.encode()
        data = {
            b'ubicacion:zona_portuaria': str(row['ZONA PORTUARIA']).encode(),
            b'ubicacion:sociedad_portuaria': str(row['SOCIEDAD PORTUARIA']).encode(),
            b'operacion:tipo_servicio': str(row['TIPO DE SERVICIO']).encode(),
            b'operacion:tipo_carga': str(row['TIPO DE CARGA']).encode(),

   b'movimiento:exportacion': str(row['EXPORTACION']).encode(),
            b'movimiento:importacion': str(row['IMPORTACIÓN']).encode(),
            b'movimiento:transbordo': str(row['TRANSBORDO']).encode(),
            b'movimiento:transito_internacional': str(row['TRANSITO INTERNACIONAL']).encode(),
            b'movimiento:fluvial': str(row['FLUVIAL']).encode(),
            b'movimiento:cabotaje': str(row['CABOTAJE']).encode(),
            b'movimiento:movilizaciones_bordo': str(row['MOVILIZACIONES A BORDO']).encode(),
            b'movimiento:transitoria': str(row['TRANSITORIA']).encode(),

   b'vigencia:anio': str(row['AÑO VIGENCIA']).encode(),
            b'vigencia:mes': str(row['MES VIGENCIA']).encode()
        }
        table.put(row_key, data)

  print("Datos cargados exitosamente.\n")

# 5. Consultas básicas

   print("Puertos con exportación mayor a 100000 toneladas:")
    for key, data in table.scan():
        try:
            export = float(data[b'movimiento:exportacion'].decode())
            if export > 100000:
                print(f"{key.decode()} → Exportación: {export}")
        except:
            continue

 print("\nRegistros de 'SOCIEDAD PORTUARIA REGIONAL DE BUENAVENTURA':")
    for key, data in table.scan():
        sociedad = data[b'ubicacion:sociedad_portuaria'].decode()
        if 'BUENAVENTURA' in sociedad:
            print(f"{key.decode()} → Sociedad: {sociedad}")

# 6. Inserción de nuevo registro

  print("\nInsertando nuevo registro ficticio...")
    table.put(b'puerto_ficticio', {
        b'ubicacion:zona_portuaria': b'ZONA X',
        b'ubicacion:sociedad_portuaria': b'PUERTO FICTICIO',
        b'operacion:tipo_servicio': b'EXPORTACION',
        b'operacion:tipo_carga': b'GENERAL',
        b'movimiento:exportacion': b'250000',
        b'movimiento:importacion': b'2000',
        b'vigencia:anio': b'2025',
        b'vigencia:mes': b'Mayo'
    })
    print("Registro insertado.")

 # 7. Actualización
  print("\nActualizando exportación de 'puerto_0' a 999999...")
    table.put(b'puerto_0', {
        b'movimiento:exportacion': b'999999'
    })
    print("Registro actualizado.")

# 8. Eliminación

  print("\nEliminando registro 'puerto_ficticio'...")
    table.delete(b'puerto_ficticio')
    print("Registro eliminado.")

except Exception as e:
    print(f"Error: {e}")

finally:
    connection.close()
    print("Conexión cerrada.")


