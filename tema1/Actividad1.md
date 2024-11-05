Esta activida consta de 3 apartados.

# Primer apartado
Con las primeras líneas de códgio verificaremos si el número argumentos es diferente de 1, las 2 siguientes, la del else y el echo es la respuesta si la verificación
da como válida, a continuación buscaremos Listen<puerto> en el archivo de /etc/apache2/ports.conf y el 1 del Listen se refiere al primer argumento del script,
por último verificaremos el resultado del Grep, si da 0 significa que el puerto ya está configurado en ports.conf, por lo que se imprime 
"Listen ya encontrado en ports.conf" y si no significa que el puerto no está presente. Entonces, el script imprime "Listen añadido" y
añade la línea Listen <puerto> al final del archivo ports.conf
 
```bash
if["$#" -ne "1"]
then
	echo "falta num puerto"
else 
	echo "correcto"
	GREP "LISTEN$1" "/etc/apache2/ports.conf"
	if["$?" eq 0]
	then
		echo "Listen ya encontrado en ports.conf"
	else
		echo "Listen añadido"
		echo "Listen $1" >> "/etc/apache2/ports.conf"
	fi

fi
```
