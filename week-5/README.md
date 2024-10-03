# OPENSHIFT DEMO

Openshift Address: https://console-openshift-console.apps.ocpquademo.quasys.com.tr

## Login Openshift

![image](https://github.com/user-attachments/assets/25f4e6fe-798b-4d7c-b6fa-9e8980ca7cd6)

Openshift'e login için "Demo-Login" butonu ve sonrasında username-password ile giriş yapılır.

## Openshift Console

Openshift'e login olduktan sonra, Administrator view a geçiş yapılır.


![image](https://github.com/user-attachments/assets/c36563d9-48f7-4a42-8615-f49b1bd21d09)


Demo'nun yapılacağı namespace'e geçmek için, Home > Projects > demo-namespace* seçilir

![image](https://github.com/user-attachments/assets/fb442c98-fd01-4bab-9c73-5619aa6b22dc)
![image](https://github.com/user-attachments/assets/49182d4a-c294-43e8-9b81-5a1a69bce97d)


## Openshift Konsol Bileşenleri

### Projects/Namespaces

Kubernetes deki namespace objesi openshift de project olarak geçmektedir.
Home > Projects kısmından mevcut namespace'ler görüntülenebilir. Kullanıcılar sadece kendi namespacelerinde yetkili olduklarından, sadece 1 namespace listelenmektedir. 

![image](https://github.com/user-attachments/assets/ae24abb5-74e2-4969-8d3b-3e90941b4405)

## Workloads

Workloads menüsü altından pod, deployment, statefulset, secrets, configmap, daemonset gibi openshift-kubernetes resourceları görüntülenebilir/yaratılabilir/değiştirilebilir.

![image](https://github.com/user-attachments/assets/1e6a017b-6544-4c0a-b162-4bfc8b6a0807)

## Networking

Networking menüsü altından service, ingress, route gibi openshift-kubernetes resourceları görüntülenebilir/yaratılabilir/değiştirilebilir.

![image](https://github.com/user-attachments/assets/2618171e-2134-47f9-b286-945e66aecbc8)

## Storage

Storage menüsü altından, statefull uygulamaların persistentvolume, persistentvolumeclaim gibi bileşenler sayesinde disk attach işlemleri sağlanır. 

![image](https://github.com/user-attachments/assets/26638ea6-6775-436f-97ec-bfce8c22fad2)


## Cli Terminal

"kubectl" ve "oc" komut satırlarını kullanmak için, openshift web-terminaline sağ üstte bulunan simgeye tıklayarak erişebilirsiniz.

![image](https://github.com/user-attachments/assets/4f371167-52a1-4862-bf5b-94ca1969a29e)

Açılan terminalde, demo-namespace* ile başlayan proje seçilir ve start edilir.

![image](https://github.com/user-attachments/assets/ab6c73ee-67e7-47dc-8ed0-17e260848c57)

Web terminal açıldıktan sonra "kubectl" ve "oc" komutları kullanılabilir.

![image](https://github.com/user-attachments/assets/e4fbaefa-d574-453d-9253-6200392d820f)

## Deployment

Konsol üzerinde Workloads > Deployments a geçilir. Gelen ekranda "Create Deployment" a tıklanır.

![image](https://github.com/user-attachments/assets/5ef3f314-de83-4dca-92c7-54f561435613)

YAML view'a geçilerek, https://raw.githubusercontent.com/quasys-tech/container-k8s-101/refs/heads/main/week-2/Kubernetes-Resources/k8s-intro-nginx-deployment.yml linkinde bulunan yaml dosyası ilgili alana yapıştırılır.

![image](https://github.com/user-attachments/assets/e88e8d45-8d71-437b-a401-845f972ddfd0)


Workloads > Pods menüsünden veya Web Terminal aracılığı ile POD'ların running durumda olup olmadıkları kontrol edilir. 

Web terminal üzerinden mevcut podları görmek için "kubectl get pods" komutu kullanılabilir.


![image](https://github.com/user-attachments/assets/53f8cf2e-6189-431d-aa25-0c07b439b570)

Pod'un detaylarına, Workloads > Pods ekranından podun ismine tıklanarak ulaşılabilir.

Details Tab'ında Pod ile ilgili genel bilgiler bulunur. Pod'un adı, Statüsü, Pod IP adresi, üzerinde çalıştığı Openshift Node'un IP adresi vs.

![image](https://github.com/user-attachments/assets/b8650f82-46bc-4b01-b6b4-55cf01313954)


Metrics tabında pod ile ilgili performans metriklerine ve kaynak kullanım detaylarına ulaşılabilir.

![image](https://github.com/user-attachments/assets/9698a09f-c599-4f8b-91a8-51af94eea13a)


YAML tabından çalışan pod'un yaml dosyasına ulaşılabilir. Mevcut konfigürasyon ile ilgili bilgiler ve statü bilgileri de yaml da bulunur.


![image](https://github.com/user-attachments/assets/20feb5b9-7f68-4be8-bfac-78aaefc0d134)


Environment Tabında, pod'un kullandığı environment variable lar var ise bunlar ile ilgili detaylar görülebilir.


![image](https://github.com/user-attachments/assets/ec887556-3a04-44e5-a06c-6813e34766f5)


Logs tabından, çalışan podun STDOUT a gönderdiği tüm çıktılar izlenebilir. Pod restart olursa bu podlar da kaybolur.
Eğer Pod içerisinde birden fazla container var ise, containerlar seçilerek de ilgili container'a ait loglara erişilebilir.


![image](https://github.com/user-attachments/assets/4f105a79-1e2c-4790-a561-59178babc92d)


Terminal Tab'ından çalışan pod'un komut satırına bağlanılabilir.

![image](https://github.com/user-attachments/assets/e8ead9e3-de98-46ca-9ad2-d91488729665)


Pod'un terminalinde "hostname" "ps -ef" gibi komutlar çalıştırılarak çıktıları incelenebilir.


![image](https://github.com/user-attachments/assets/e0ff25c8-1a4f-4966-bb94-ec2305599bbb)

