# Домашнее задание к занятию «Запуск приложений в K8S» Стасенко Григорий Мирайлович

### Цель задания

В тестовой среде для работы с Kubernetes, установленной в предыдущем ДЗ, необходимо развернуть Deployment с приложением, состоящим из нескольких контейнеров, и масштабировать его.

------

### Чеклист готовности к домашнему заданию

1. Установленное k8s-решение (например, MicroK8S).
2. Установленный локальный kubectl.
3. Редактор YAML-файлов с подключённым git-репозиторием.

------

### Инструменты и дополнительные материалы, которые пригодятся для выполнения задания

1. [Описание](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) Deployment и примеры манифестов.
2. [Описание](https://kubernetes.io/docs/concepts/workloads/pods/init-containers/) Init-контейнеров.
3. [Описание](https://github.com/wbitt/Network-MultiTool) Multitool.

------

### Задание 1. Создать Deployment и обеспечить доступ к репликам приложения из другого Pod

1. Создать Deployment приложения, состоящего из двух контейнеров — nginx и multitool. Решить возникшую ошибку.

<img width="463" height="115" alt="image" src="https://github.com/user-attachments/assets/688d3dcb-1247-4668-8dbc-b4a62e5d8981" />
<img width="898" height="309" alt="image" src="https://github.com/user-attachments/assets/7929e233-8136-4e0a-bd1d-eaa871ab2c1e" />
<img width="446" height="551" alt="image" src="https://github.com/user-attachments/assets/f8cb790a-c06c-42c3-94f0-00bd1fbf63e7" />

<img width="531" height="114" alt="image" src="https://github.com/user-attachments/assets/7e2863ac-f728-448b-a963-f6e3e2e6b924" />



2. После запуска увеличить количество реплик работающего приложения до 2.
3. Продемонстрировать количество подов до и после масштабирования.

<img width="479" height="67" alt="image" src="https://github.com/user-attachments/assets/984c98ee-1d23-4207-a8bc-8d0905cd9341" />
<img width="483" height="102" alt="image" src="https://github.com/user-attachments/assets/5acf3cdf-86b4-44c0-abb5-869965629551" />

4. Создать Service, который обеспечит доступ до реплик приложений из п.1.

<img width="913" height="581" alt="image" src="https://github.com/user-attachments/assets/2791dc85-2eab-428e-8b4e-592958a7dc8c" />
 
5. Создать отдельный Pod с приложением multitool и убедиться с помощью `curl`, что из пода есть доступ до приложений из п.1.

<img width="431" height="93" alt="image" src="https://github.com/user-attachments/assets/8a6abc7d-0651-4708-b239-79194f0dafac" />
<img width="596" height="296" alt="image" src="https://github.com/user-attachments/assets/be7a6cce-ca2c-478f-89c6-4f9d34e2cfcb" />
<img width="583" height="311" alt="image" src="https://github.com/user-attachments/assets/2523dfe6-417d-4f46-b446-f3bdc9bccc80" />
<img width="906" height="529" alt="image" src="https://github.com/user-attachments/assets/f1037b9e-f83e-4775-b2a3-918878f18a58" />
<img width="911" height="479" alt="image" src="https://github.com/user-attachments/assets/a909c5b4-fa2f-4a37-9327-fe17897d8077" />

------

### Задание 2. Создать Deployment и обеспечить старт основного контейнера при выполнении условий

1. Создать Deployment приложения nginx и обеспечить старт контейнера только после того, как будет запущен сервис этого приложения.
2. Убедиться, что nginx не стартует. В качестве Init-контейнера взять busybox.

<img width="476" height="110" alt="image" src="https://github.com/user-attachments/assets/ada9f2a8-b90f-4fb6-9900-1f0647f4d367" />

3. Создать и запустить Service. Убедиться, что Init запустился.
4. Продемонстрировать состояние пода до и после запуска сервиса.

<img width="487" height="242" alt="image" src="https://github.com/user-attachments/assets/8ce3c5f2-6269-41ee-8646-54fdc18b2961" />

------

### Правила приема работы

1. Домашняя работа оформляется в своем Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд `kubectl` и скриншоты результатов.
3. Репозиторий должен содержать файлы манифестов и ссылки на них в файле README.md.
