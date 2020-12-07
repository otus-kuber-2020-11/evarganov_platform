FROM nginx:mainline-alpine
RUN adduser -D -u 1001 -g 'www' www
WORKDIR /app
RUN chown -R www:www /app/
COPY nginx.conf /etc/nginx/nginx.conf
EXPOSE 8000