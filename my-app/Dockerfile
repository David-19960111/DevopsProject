#Imagen oficial de Node.js
FROM node:14 

#Directorio de trabajo
WORKDIR /app

#Copiar archivos package.json y package-lock.son
COPY package*.json ./ 

#Instalar las dependencias del proyecto
RUN npm install 

#Copia el resto de los archivos del proyecto
COPY . .

#Añade un usuario y grupo no privilegiados
RUN groupadd -r devopsbasic && useradd -r -g appgroup david 

#Establece los permisos para el directorio de trabajo
RUN chown -R david:devopsbasic /app 

#Cambia al usuario no privilegiado
USER david 

#Expone el puerto de la aplicacion
EXPOSE 3000 

#Comando para iniciar la aplicacion
CMD ["npm", "start"]