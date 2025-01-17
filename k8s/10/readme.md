# Домашнее задание к занятию «Helm»

### Цель задания

В тестовой среде Kubernetes необходимо установить и обновить приложения с помощью Helm.

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение, например, MicroK8S.
2. Установленный локальный kubectl.
3. Установленный локальный Helm.
4. Редактор YAML-файлов с подключенным репозиторием GitHub.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Инструкция](https://helm.sh/docs/intro/install/) по установке Helm. [Helm completion](https://helm.sh/docs/helm/helm_completion/).

------

### Задание 1. Подготовить Helm-чарт для приложения

1. Необходимо упаковать приложение в чарт для деплоя в разные окружения. 
2. Каждый компонент приложения деплоится отдельным deployment’ом или statefulset’ом.
3. В переменных чарта измените образ приложения для изменения версии.

------

### Задание 2. Запустить две версии в разных неймспейсах

1. Подготовив чарт, необходимо его проверить. Запуститe несколько копий приложения.
2. Одну версию в namespace=app1, вторую версию в том же неймспейсе, третью версию в namespace=app2.
3. Продемонстрируйте результат.

### Решение 1. Подготовить Helm-чарт для приложения

1. устанавливаю **Helm**  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/01.png)  
2. создаю helm nginx командой **helm create nginx**  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/02.png)  
3. вывод REVISION 1  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/03.png)  
4. вывод REVISION 2  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/04.png) 
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/05.png)   

------

### Задание 2. Запустить две версии в разных неймспейсах

1. создал 2 namespace app1 & app2  
2. nginx в ns app1
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/06.png)  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/07.png)   
3. nginx в ns app2
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/08.png) 
4. вывод:  
![markdown img](https://github.com/MezencevPavel/devops-netology/blob/main/k8s/10/png/09.png) 

------