# 🧠 Building a Real-Time Serverless Quiz Platform (Kahoot-style) on AWS  
### Arquitectura, decisiones y lecciones aprendidas

---

## 🌍 Introducción

Construir una plataforma de exámenes online en tiempo real parece sencillo… hasta que necesitas:

- Sincronizar cientos de usuarios en vivo  
- Garantizar baja latencia  
- Mantener consistencia sin estado compartido  
- Escalar sin servidores dedicados  

Este proyecto nace con un objetivo claro:

> **Diseñar una plataforma tipo Kahoot completamente serverless, escalable y orientada a eventos sobre AWS.**

---

## 🏗️ Arquitectura

```
Frontend (Angular)
        │
        ├── API Gateway (REST)
        │        └── AWS Lambda
        │
        └── API Gateway (WebSocket)
                 └── AWS Lambda (Actions)
                          │
                          ├── DynamoDB
                          └── SQS
```

---

## ⚙️ Servicios AWS utilizados

- API Gateway (REST + WebSocket)
- AWS Lambda
- DynamoDB
- SQS
- AWS SAM
- CloudWatch
- GitHub Actions

---

## 🎮 Flujo del juego

![alt text](image-2.png)

1. Host inicia juego  
![alt text](<Screenshot 2026-02-01 134010.png>)
2. Se cargan preguntas  
3. Se distribuye a jugadores  
4. Jugadores responden  
![alt text](<Screenshot 2026-03-17 063957.png>)
5. Se calcula ranking  
6. Se muestra podio  

![alt text](image.png)
---

## 🧠 Principios clave

- Estado externo en DynamoDB  
- Arquitectura event-driven  
- Separación REST vs WebSocket  
- Escalabilidad serverless  

---

## 🚀 Conclusión

Arquitectura moderna basada en:

- Serverless  
- Event-driven  
- Tiempo real  

![alt text](image-1.png)
---

## 👨‍💻 Autor

Paul Rivera
AWS Certified Solutions Architect
