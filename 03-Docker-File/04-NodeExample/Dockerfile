# İlk olarak image bilgisini yazıyoruz.
FROM node:16.5-alpine

# Environment tanımlamak.
ENV NODE_ENV=production
ENV PORT=3000

# Paket dosyalarının json bilgisini containere kopyalanması.
COPY . /app

# Çalışma dizininin belirlenmesi.
WORKDIR /app

# Bağımlılıkların container node_modules'e yüklenmesi.
RUN npm install

# Yayın yapılacak port.
EXPOSE 3000

# Çalıştırmak.
ENTRYPOINT ["npm", "start"]

# Run command in cmd
# docker image build --tag nodex .
# docker run -d -p 8080:3000 --name nodex nodex
# docker container exec nodex ls
