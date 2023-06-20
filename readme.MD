# Create nginx-proxy-manager Dashboard
`cd nginx-proxy-manager`

`docker compose up -d`


Access this url: `http://127.0.0.1:81`
* Default Proxy Manager username: `admin@example.com`
* Default Proxy Manager password: `changeme`

# Create example app

> **Note: Các app bắt buộc phải chung network `nginx-proxy-manager-network`**

`docker compose -f docker-compose-tulipnginx.yml up -d`

Sử dụng command `docker ps`, thấy 1 container nginx-proxy-manager và 1 container nginx để làm example.

# Create Proxy Host in Dashboard
> **Note:**
> 
> Hosts => Proxy Hosts => Add Proxy Host
> 
> Domain Names -> example.com
> 
> Scheme -> http
> 
> Forward Hostname / IP -> Tên service trong docker compose file
> 
> Forward Port -> port của container (docker ps)

Thêm dòng sau vào file host:

`127.0.0.1 example.com`

Access `example.com` để thấy trang default của nginx example
