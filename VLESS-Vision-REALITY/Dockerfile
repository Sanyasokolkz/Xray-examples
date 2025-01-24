# Используем минимальный образ Linux
FROM alpine:latest

# Устанавливаем необходимые зависимости
RUN apk add --no-cache bash curl jq

# Скачиваем Xray
RUN curl -L -o /xray.zip https://github.com/XTLS/Xray-core/releases/latest/download/Xray-linux-64.zip && \
    unzip /xray.zip -d /xray && rm /xray.zip

# Копируем конфигурацию в контейнер
COPY config_server.json /xray/config.json

# Открываем порт 443
EXPOSE 443

# Запуск Xray
CMD ["/xray/xray", "-config", "/xray/config.json"]
