# TEK AŞAMALI YÖNTEM
# Base Image
# FROM python:3.9.6-alpine

# Container içerisinde çalışma dizini belirle
# WORKDIR /app

# Bağımlılıkları içeren dosyayı container'e kopyala
# COPY ./requirements.txt .

# Bağımlılıkları yükle
# RUN pip install -r requirements.txt

# Lokaldeki proje dosyalarını container içerisine kopyala
# COPY . .

# Container başladığında uygulamayı çalıştır.
# CMD python ./server.py

# Open command line
# docker image build --tag flaskx .
# docker container run -dp 5000:5000 --name flaskx flaskx
# docker container exec flaskx ls

# ÇOK AŞAMALI YÖNTEM

# İlk aşama

# image dosyası seç
FROM python:3.9.6-alpine as base
COPY requirements.txt .

# bağımlılıkları kullanıcı alanına yükle
RUN pip install --user -r requirements.txt

# İkinci aşama
FROM python:3.9.6-alpine
WORKDIR /app

# Birici aşamadaki bağınlılıkları kopyala
COPY --from=base /root/.local /root/.local
COPY . .

# PATH bilgisini güncelle
ENV PATH=/root/.local:$PATH
CMD python ./server.py
