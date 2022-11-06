# Сервис для расчета рыночной стоимости жилой недвижимости города Москвы

## Навигация

- [Описание проекта](#desc)
- [Стек технологий](#stack)
- [Сборка проекта](#launch)
- [Документация](#docs)
- [Лицензия](#license)

<a name="desc"></a>

## Описание проекта

Разработайте сервис, который автоматизирует процесс расчета стоимости однотипных квартир, находящихся в собственности города, в зависимости от их индивидуальных параметров. Сервис позволит ускорить процедуру выдачи экспертных заключений о стоимости квартир и избежать сделок, при которых городское имущество продается по цене ниже рыночной

<a name="stack"></a>

## Стек технологий

- Frontend:
  [![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)](https://reactjs.org/)
  [![Next](https://img.shields.io/badge/Next-FFF?logo=nextdotjs&logoColor=black)](https://nextjs.org/)
  [![MobX](https://img.shields.io/badge/Mobx-764ABC?logo=mobx&logoColor=white)](https://mobx.js.org/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
- Backend:
  [![Fast API](https://img.shields.io/badge/FastAPI-009485?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
  [![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
- Parser:
  [![Fast API](https://img.shields.io/badge/FastAPI-009485?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
  [![Selenium](https://img.shields.io/badge/Selenium-43B02A.svg?logo=selenium&logoColor=white)](https://www.selenium.dev/)
- Proxy:
  [![Nginx](https://img.shields.io/badge/Nginx-009639.svg?logo=nginx&logoColor=white)](https://nginx.org/)
- Work:
  [![Figma](https://img.shields.io/badge/Figma-F24E1E?logo=figma&logoColor=white)](https://www.figma.com/)
  [![Docker](https://img.shields.io/badge/Docker-%230db7ed.svg?logo=docker&logoColor=white)](https://www.docker.com/)

<a name="launch"></a>

## Сборка проекта

### Production

1. Склонируйте данный репозиторий:

```sh
git clone https://github.com/mirea-ninja/lct-hack.git lct-hack --recursive
cd lct-hack
```

2. Отредактируйте `.env.example`:

```sh
# Deploy
BACKEND_ALLOWED_DOMAINS=YOUR_BACKEND_ALLOWED_DOMAINS

# Debug
DEBUG=False

# Frontend
NEXT_APP_API_URL=YOUR_API_URL
NEXT_APP_PARSER_API_URL=YOUR_PARSER_API_URL

# Backend
BACKEND_TTILE='LCT Hack Backend'
BACKEND_DESCRIPTION='Backend part for LCT Hack'
BACKEND_PREFIX=/api

BACKEND_HOST=0.0.0.0
BACKEND_PORT=80
BACKEND_RELOAD=False

BACKEND_CORS_ORIGINS=["http://localhost"]

BACKEND_JWT_SECRET=Y0UR_JWT_SECRET
BACKEND_JWT_ALGORITHM=HS256
BACKEND_JWT_ACCESS_TOKEN_EXPIRE_MINUTES=20160 # 7 * 24 * 60

BACKEND_DADATA_TOKEN=Y0UR_DADATA_TOKEN

# Feature Switch
BACKEND_DISABLE_AUTH=False
BACKEND_DISABLE_FILE_SENDING=False
BACKEND_DISABLE_REGISTRATION=False

# Storage
STORAGE_REGION=Y0UR_STORAGE_REGION
STORAGE_ENDPOINT=Y0UR_STORAGE_ENDPOINT
STORAGE_ACCESS_KEY=Y0UR_STORAGE_ACCESS_KEY
STORAGE_ACCESS_KEY_ID=Y0UR_STORAGE_ACCESS_KEY_ID
STORAGE_BUCKET_NAME=Y0UR_STORAGE_BUCKET_NAME
STORAGE_FOLDER_NAME=Y0UR_STORAGE_FOLDER_NAME

# PostgreSQL
POSTGRES_SERVER=db
POSTGRES_USER=Y0UR_POSTGRES_USER
POSTGRES_PASSWORD=Y0UR_POSTGRES_USER
POSTGRES_DB=Y0UR_POSTGRES_DB
```

3. Переименуйте `.env.example` в `.env`
4. Запустите проект с помощь Docker Compose:

```sh
docker-compose up -d --build
```

5. Перейдите в директорию парсера:

```sh
cd parser
```

6. Отредактируйте `.env.example`:

```sh
# Debug
DEBUG=False

# Deploy
BACKEND_ALLOWED_DOMAINS=YOURSITE.RU

# Application
BACKEND_TTILE='LCT Hack Parser'
BACKEND_DESCRIPTION='Parser part for LCT Hack'
BACKEND_PREFIX=/api

BACKEND_HOST=0.0.0.0
BACKEND_PORT=8080
BACKEND_RELOAD=True

BACKEND_CORS_ORIGINS='["http://localhost:8080", "http://localhost:8081"]'

BACKEND_JWT_SECRET=YOUR_BACKEND_JWT_SECRET
BACKEND_JWT_ALGORITHM='HS256'

BACKEND_DADATA_TOKEN=YOUR_BACKEND_DADATA_TOKEN

BACKEND_AUTH_TOKEN=YOUR_BACKEND_AUTH_TOKEN
BACKEND_API_URL=YOUR_BACKEND_API_URL

# Selenium
SE_NODE_OVERRIDE_MAX_SESSIONS=1
SE_NODE_MAX_SESSIONS=16
```

7. Переименуйте `.env.example` в `.env`
8. Запустите проект с помощь Docker Compose:

```sh
docker-compose up -d --build
```

<a name="docs"></a>

## Документация

- Документация серверной части доступна по адресу: [lct.mirea.ninja/redoc](https://lct.mirea.ninja/redoc)
- Документация парсера доступна по адресу: [parser.lct.mirea.ninja/redoc](https://parser.lct.mirea.ninja/redoc)

### Endpoints

- Frontend - [lct.mirea.ninja](https://lct.mirea.ninja)
- Backend - [lct.mirea.ninja/api](https://lct.mirea.ninja/api)
- Parser - [parser.lct.mirea.ninja](https://parser.lct.mirea.ninja/api)
- Backend Swagger - [lct.mirea.ninja/docs](https://lct.mirea.ninja/docs)
- Backend Parser - [parser.lct.mirea.ninja/docs](https://parser.lct.mirea.ninja/docs)

<a name="license"></a>

## Лицезия

- [MIT](LICENSE)
