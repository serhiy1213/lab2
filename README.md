1. Реєстрації на AWS
2. Встановити terraform
3. Створення config.tf файлу
В нього я помістив ось такий код

![image](https://user-images.githubusercontent.com/113981423/201170017-4b5788c6-0736-4512-84e1-5e0dc72cbde3.png)

![image](https://user-images.githubusercontent.com/113981423/201170045-b298b35f-75f8-44e4-a81b-f2f160d60744.png)

Прописав terraform init та terraform apply

![image](https://user-images.githubusercontent.com/113981423/201170809-214c9f24-6d10-44cf-8073-a98e8b7a11b8.png)

Встановив nginx

![image](https://user-images.githubusercontent.com/113981423/201172651-7d403737-24b2-4574-89ec-9347d5c9ccc1.png)

Переходячи по силці http://54.221.142.158/lab2/ бачимо html сторінку

![image](https://user-images.githubusercontent.com/113981423/201172126-9a05678c-70db-4747-8ef2-5e49523ee7b5.png)

provider "aws" {
    access_key = "..."
    secret_key = "..."
    region = "us-east-1"
}

resource "aws_instance" "my_ubuntu" {
    ami = "ami-08c40ec9ead489470"
    instance_type = "t2.micro"
    vpc_security_group_ids = [aws_security_group.my_web_security_group.id]
    key_name = "my_key"

    tags = {
        Name = "MyServer"
        Owner = "Oliyarnik Serhiy"
        Project = "Lab4"
    }
}

resource "aws_security_group" "my_web_security_group" {
    name = "Security group"
    description = "allow http and https"

    ingress {
        from_port = 80
        to_port = 80
        protocol = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
    }

    ingress {
        from_port = 443
        to_port = 443
        protocol = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
    }

    ingress{
        from_port = 22
        to_port = 22
        protocol = "tcp"
        cidr_blocks = ["0.0.0.0/0"]
    }

    egress {
        from_port = 0
        to_port = 0
        protocol = "-1"
        cidr_blocks = ["0.0.0.0/0"]
    }

}

resource "aws_key_pair" "keys" {
        key_name = "my_key"
        public_key = "ssh-rsa ..."
    }

Висновок: на даній лабораторній роботі я завдяки terraform зміг створити власний сервер

