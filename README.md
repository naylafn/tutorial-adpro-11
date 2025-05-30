# Tutorial Pemrograman Lanjut
## Nayla Farah Nida - 2306213426

### Module 11

1. Compare the application logs before and after you exposed it as a Service.

Sebelum expose:

![Before exposing as service](logs-before-exposed.png)

Log menunjukkan bahwa server HTTP dimulai di port 8080 dan server UDP di port 8081.

Setelah expose:

![After exposing as service](logs-after-exposed.png)

Log tambahan menunjukkan ada permintaan GET ke server HTTP pada pukul 10:05:07, yang menunjukkan bahwa expose telah membuat aplikasi dapat diakses melalui load balancer pada port 8080. Setelah kubectl expose, aplikasi dapat diakses dari luar cluster, terlihat dari adanya permintaan GET yang tercatat di log.

![After running the app several times](logs-after-running-apps.png)

Jumlah log meningkat setiap kali aplikasi dibuka. Setiap permintaan GET yang dilakukan ke server HTTP tercatat di log, menunjukkan bahwa aplikasi merespons setiap akses yang dilakukan.

2. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

Opsi ```-n``` pada perintah kubectl get digunakan untuk menentukan namespace tempat sumber daya yang ingin dilihat. Di Kubernetes, namespace memungkinkan pengelompokan sumber daya dalam kelompok terpisah. Ketika tidak menyertakan opsi ```-n```, kubectl secara default akan mencari sumber daya di namespace default. Alasan mengapa pod/service yang dibuat secara eksplisit tidak muncul saat menggunakan ```-n kube-system``` adalah karena pod/service tersebut kemungkinan dibuat di namespace yang berbeda, bukan di namespace kube-system, yang biasanya berisi sumber daya sistem.
