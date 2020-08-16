# Hướng dẫn cài đặt Docker trên Ubuntu

Docker là một nền tảng để cung cấp cách để building, deploying và running ứng dụng dễ dàng hơn bằng cách sử dụng các containers. Hướng dẫn này nhằm mục đích thiết lập và cài đặt Docker trên Ubuntu.

![Hướng dẫn cài đặt Docker trên Ubuntu](https://techfinally.com/wp-content/uploads/2020/08/techfinally-huong-dan-cai-dat-docker-tren-ubuntu.jpg)

##1. Hướng dẫn cài đặt Docker trên Ubuntu

Đầu tiên tiến hành cập nhật hệ thống

```
sudo apt update
```

Tiếp theo cài đặt một vài gói cho phép apt sử dụng các gói qua HTTPS

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```

Thêm khóa GPG cho kho lưu trữ Docker chính thức vào hệ thống

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

Thêm kho lưu trữ Docker vào các nguồn APT

```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

Sau khi thêm kho lưu trữ Docker thì bạn tiến hành cài đặt Docker trên Ubuntu

```
sudo apt update
```

Đảm bảo rằng bạn cài đặt từ kho Docker thay vì kho mặc định của Ubuntu

```
apt-cache policy docker-ce
```

Cuối cùng là thực hiện cài đặt Docker

```
sudo apt install docker-ce
```

Khi quá trình cài đặt Docker trên Ubuntu hoàn tất thì dịch vụ Docker sẽ tự khởi động. Chúng ta sẽ kiểm tra việc cài đặt đã thành công hay chưa, số phiên bản cho Docker có thể khác nhau.

```
sudo systemctl status docker
```

![Hướng dẫn cài đặt Docker trên Ubuntu](https://techfinally.com/wp-content/uploads/2020/08/techfinally-huong-dan-cai-dat-docker-tren-ubuntu-h01-1024x350.jpg)

##2.Thiết lập thực thi lệnh Docker mà không sử dụng SUDO

Nếu bạn muốn tránh nhập sudo khi chạy lệnh docker, hãy thêm tên người dùng của bạn vào nhóm docker

```
sudo usermod -aG docker ${USER}
```

Để áp dụng tư cách thành viên nhóm mới, hãy đăng xuất khỏi máy chủ và đăng nhập lại hoặc nhập như sau

```
su - ${USER}
```

Nếu bạn cần thêm người dùng vào nhóm docker mà bạn chưa đăng nhập, hãy khai báo tên người dùng đó một cách rõ ràng bằng cách sử dụng

```
sudo usermod -aG docker <username>
```

Hãy thay <username> bằng USER của bạn muốn sử dụng.

##3. Ví dụ khởi chạy Hello World trên Docker

```
docker run hello-world
```

Kết quả sau khi chạy lệnh trên

![Hướng dẫn cài đặt Docker trên Ubuntu](https://techfinally.com/wp-content/uploads/2020/08/techfinally-huong-dan-cai-dat-docker-tren-ubuntu-h02-1024x382.jpg)

Nguồn: [Hướng dẫn cài đặt Docker trên Ubuntu](https://techfinally.com/huong-dan-cai-dat-docker-tren-ubuntu/)
