# bingpt_docker

- [中文](./README.md)
- [ENGLISH](./README_EN.md)

- [Github](https://github.com/niliovo/bingpt_docker)
- [Docker Hub](https://hub.docker.com/r/niliaerith/bingpt)

# 本项目基于下列项目，将 PandoraAI 集成到docker镜像

- [PandoraAI](https://github.com/waylaidwanderer/PandoraAI)

## Docker-Cli使用指南

```bash
docker run -itd --name bingpt --hostname bingpt --net bridge -p 3001:3000 --restart always -v /your_path/bingpt/.env:/pandora-ai/.env -v /your_path/bingpt/nuxt.config.js:/pandora-ai/nuxt.config.js -e API_BASE_URL=https://www.example.com niliaerith/bingpt:latest
```

## Docker Compose使用指南

- bingpt

```compose.yml
  bingpt:
    image: niliaerith/bingpt:latest
    container_name: bingpt
    hostname: bingpt
    restart: always
    network_mode: bridge
    ports:
      - 3001:3000
    environment:
      - API_BASE_URL=https://www.example.com
    volumes:
      - /your_path/bingpt/.env:/pandora-ai/.env
      - /your_path/bingpt/nuxt.config.js:/pandora-ai/nuxt.config.js
```

## 变量

> 必须变量
- `-v /your_path/bingpt/.env:/pandora-ai/.env`  或 `-e API_BASE_URL=https://www.example.com`
- - `-v /your_path/bingpt/.env:/pandora-ai/.env`文件为API接口配置文件,默认值为`API_BASE_URL=http://localhost:3000`，第一次运行自动生成，请自行修改。或添加环境变量 `-e API_BASE_URL=https://www.example.com`

> 可选变量
- `-v /your_path/bingpt/nuxt.config.js:/pandora-ai/nuxt.config.js`
- - `nuxt.config.js`文件为nuxt配置文件，可修改标题等

## 支持平台

- amd64
- arm64

# 感谢

- [@waylaidwanderer/PandoraAI](https://github.com/waylaidwanderer/PandoraAI)
- [GitHub](https://github.com/)
- [Docker Hub](https://hub.docker.com/)
- [中科大源](https://mirrors.ustc.edu.cn/)