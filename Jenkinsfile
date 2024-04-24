import java.text.SimpleDateFormat
resultadoAritmeticas = ""
pipeline
{
    agent any
    options
    {
        timeout(time:5, unit: 'MINUTES')
    }
    
    environment
    {
        filePath = "C:\\Users\\alejandro.santana\\Documents\\AlejandroSantanaAmador\\Archivo_Ejercicio3.txt"
    }
    stages {
        stage('Operaciones_Aritmeticas') {
            steps {
                script {
                    numero1 = 10
                    numero2 = 2
                    resultSum = numero1 + numero2
                    resultRes = numero1 - numero2
                    resultMult = numero1*numero2
                    resultDiv = numero1/numero2
                    resultadoAritmeticas = resultadoAritmeticas + "numero1 = " + numero1 + "\n" + "numero2 = " + numero2 + "\n" + "Suma: " + resultSum + "\n" + "Resta: " + resultRes + "\n" + "Multiplicacion: " + resultMult + "\n" + "Division: " + resultDiv + "\n"
                    echo resultadoAritmeticas
                }
            }
        }
        stage('flush')
        {
            steps
            {
                bat "ipconfig /flushdns"
            }
        }
        stage('Fichero')
        {
            steps {
                script 
                {
                    writeFile(file:filePath, text: resultadoAritmeticas)    
                }
            }
        } 
    }
    post
    {
        always
        {
            echo "El pipeline de Ejercicio 3 se ejecuto. "
        }
        failure
        {
            echo 'EL pipeline de Ejercicio 3 fallo'
        }
        unstable
        {
            echo "El pipeline de Ejercicio 3 no se ejecuto de forma estable."
        }
        success
        {
            echo "Todo salio bien en el ejercicio 3"        
        }
    }
}
