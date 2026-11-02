FROM node:20-slim
WORKDIR /app
COPY app.tar.gz ./
RUN tar -xzf app.tar.gz && rm app.tar.gz
RUN npm install --omit=dev --no-audit --no-fund
ENV NODE_ENV=production
EXPOSE 8000
CMD ["node", "gateway.js"]
