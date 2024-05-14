# Actividad 07  
- - -  

## El programa deberá validar si el bucket ya existe o no y en caso de que no, debera crearlo y mostrar el nombre del equipo y la fecha de ejecución del programa.

~~~
#!/bin/bash

BUCKET=$(gsutil ls | grep "bkt06")


creacion(){
        gsutil mb -p sit-devops-training -c STANDARD -l US-EAST4 -b on gs://sit-devops-training-bkt06
}

validacion_bucket(){

if [ "$BUCKET" = "gs://sit-devops-training-bkt06" ]; then
        echo “Nombre repetido, no es posible continuar”
else
        creacion
        echo "Se creo el bucket"
fi
}

validacion_bucket

imprimir(){
        echo "Autobots"
        date
}

imprimir

Funcion para borrar el Bucket

borrado(){
       gsutil rm -r gs://sit-devops-training-bkt06
}

#borrado

~~~
