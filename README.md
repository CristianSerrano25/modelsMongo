# Modelado con Mongoose

En base al contexto proporcionado se procedio a realizar el modelo de las colecciones y la relacion que tendran entre si.

## Contexto

Un comercio de suministros de limpieza requiere que cada uno de sus empleados pueda
registrar sus ventas de forma individual. Además, los empleados deben tener acceso a la
aplicación utilizando credenciales.

## Resolución 

Se crearon las colecciones de "employee" , "product" , "sales" y "auth".

En la colección "sales" se referencio "employee" y "product"

```javascript
const saleSchema = new mongoose.Schema({
    product: {
        type: mongoose.Schema.Types.ObjectId,
        ref: 'Product',
        required: true
    },
    employee: {
        type: mongoose.Schema.Types.ObjectId,
        ref: 'Employee',
        required: true
    },
```
En la colección "auth" se referencio "employee" 

```javascript
const authSchema = new mongoose.Schema({
    employee: {
        type: mongoose.Schema.Types.ObjectId,
        ref: 'Employee',
        required: true,
        unique: true
    },
```
