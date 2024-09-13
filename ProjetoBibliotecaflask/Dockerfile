# Usando a imagem base do Python
FROM python:3.12

# Instalando o cliente MySQL
RUN apt-get update && \
    apt-get install -y default-mysql-client && \
    rm -rf /var/lib/apt/lists/* && \
    mkdir /app

# Definindo o diretório de trabalho
WORKDIR /app

# Copiando os arquivos de requisitos e instalando as dependências
COPY . .
RUN pip install --no-cache-dir -r requirements.txt

# Copiando o restante dos arquivos do aplicativo
# COPY . .

# Definindo a variável de ambiente para o Flask
ENV FLASK_APP=/app/app.py

# Expondo a porta que o Flask vai usar
EXPOSE 5000

# Comando para iniciar o aplicativo Flask
CMD ["flask", "run", "--host=0.0.0.0"]
 
