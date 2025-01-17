# Домашнее задание к занятию «Организация сети»

### Подготовка к выполнению задания

1. Домашнее задание состоит из обязательной части, которую нужно выполнить на провайдере Yandex Cloud, и дополнительной части в AWS (выполняется по желанию). 
2. Все домашние задания в блоке 15 связаны друг с другом и в конце представляют пример законченной инфраструктуры.  
3. Все задания нужно выполнить с помощью Terraform. Результатом выполненного домашнего задания будет код в репозитории. 
4. Перед началом работы настройте доступ к облачным ресурсам из Terraform, используя материалы прошлых лекций и домашнее задание по теме «Облачные провайдеры и синтаксис Terraform». Заранее выберите регион (в случае AWS) и зону.

---
### Задание 1. Yandex Cloud 

**Что нужно сделать**


1. Создать пустую VPC. Выбрать зону.
[providers.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/providers.tf)  
2. Публичная подсеть.  
[vpc.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/vpc.tf)  
[nat.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/nat.tf)  
[public-vm.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/public-vm.tf)  
 - Создать в VPC subnet с названием public, сетью 192.168.10.0/24.
 - Создать в этой подсети NAT-инстанс, присвоив ему адрес 192.168.10.254. В качестве image_id использовать fd80mrhj8fl2oe87o4e1.
 - Создать в этой публичной подсети виртуалку с публичным IP, подключиться к ней и убедиться, что есть доступ к интернету.
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/png/11.png)  
3. Приватная подсеть.  
[route-table.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/route-table.tf)  
[private-vm.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/private-vm.tf)  
[outputs.tf](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/source/outputs.tf)  
 - Создать в VPC subnet с названием private, сетью 192.168.20.0/24.  
 - Создать route table. Добавить статический маршрут, направляющий весь исходящий трафик private сети в NAT-инстанс.
 - Создать в этой приватной подсети виртуалку с внутренним IP, подключиться к ней через виртуалку, созданную ранее, и убедиться, что есть доступ к интернету.  
 ![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/png/12.png)  
   
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/png/01.jpg)  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/cloud/01/png/02.jpg)  
---





