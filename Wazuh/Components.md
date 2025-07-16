# Components

[🔗 Wazuh Components](https://documentation.wazuh.com/current/getting-started/components/index.html)

## Wazuh indexer

Wazuh indexer adalah highly scalable, full-text search and analytics engine. Komponen pusat ini melakukan pengindeksan dan penyimpanan alert yang dihasilkan oleh Wazuh server.

## Wazuh server

Wazuh server adalah komponen pusat yang menganalisis data yang diterima dari agent. Server ini memproses data tersebut melalui decoder dan rules, serta menggunakan threat intelligence untuk mencari indicators of compromise (IOCs) yang sudah dikenal.

Wazuh server dapat menganalisis data dari ratusan hingga ribuan agents, dan dapat diskalakan secara horizontal saat dikonfigurasi dalam bentuk cluster. Selain itu, Wazuh server juga digunakan untuk mengelola agen, termasuk melakukan konfigurasi dan pembaruan dari jarak jauh jika diperlukan.

## Wazuh dashboard

Wazuh dashboard adalah antarmuka pengguna berbasis web untuk visualisasi dan analisis data. Dashboard ini menyediakan tampilan siap pakai untuk threat hunting, regulatory compliance (seperti PCI DSS, GDPR, CIS, HIPAA, NIST 800-53), aplikasi rentan yang terdeteksi, data file integrity monitoring, hasil configuration assessment, pemantauan infrastruktur cloud, dan lainnya.

Wazuh dashboard juga digunakan untuk mengelola konfigurasi Wazuh dan memantau statusnya.

## Wazuh agent

Wazuh agents adalah perangkat lunak yang diinstal pada endpoint seperti laptop, desktop, server, instance cloud, atau mesin virtual. Agent ini mengirim log dan data sistem ke Wazuh server, serta menyediakan kemampuan untuk pencegahan, deteksi, dan respons terhadap ancaman. Mereka dapat berjalan di berbagai sistem operasi seperti Linux, Windows, macOS, Solaris, AIX, dan HP-UX.

## Wazuh Components and Data Flow Diagrams

![alt text](https://documentation.wazuh.com/current/_images/wazuh-components-and-data-flow1.png)