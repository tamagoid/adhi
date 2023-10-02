---
title: "Mengatasi Masalah Tidak Dapat Mengambil Peta Situs"
date: 2023-09-23T20:18:52+07:00
description: "mengalami masalah saat submit sitemap atau peta situs. Dimana saat melakukan submit sitemap terdapat peringatan Couldn't Fetch jika diterjemahkan berarti tidak dapat mengambil peta situs"
tags: [
    "Sitemap",
    "Blog",
]
images: ["https://images.unsplash.com/photo-1522542550221-31fd19575a2d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=2070&q=80"]
draft: false
---

Beberapa waktu yang lalu saya menemukan sebuah pertanyaan dari member grup Blogger Indonesia di Facebook, yang mengalami masalah saat _submit sitemap_ atau peta situs. Dimana saat melakukan _submit sitemap_ terdapat peringatan "Couldn't Fetch" jika diterjemahkan berarti tidak dapat mengambil peta situs . Dan ternyata masalah ini tidak hanya dialami oleh satu orang saja, tapi banyak. Banyak asumsi bermunculan alasan eror karena domainnya, templatenya, hingga menyalahkan platformnya. Meskipun bukan ahli saya jadi merasa terpanggil untuk ikut mencari solusinya.

![Sitemap Couldn't Fetch](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhLkksEzY2R8aTtQRU5Fv772Aik8umO2QJMdhpuTolYeUmGPVoBCdlvSYarpYgdF_MJ7pFqj3xMF3JXtCOhh_a84a_v-P37UvC8HdFvlfw213OR-8mHmgn9TNs9q4wdarWoM28euUITfTdGhYjTmw9FGMRHd7gLhpfTG_YoxVZQqPJnDtPzcvfA7gzKLSNG/s892/tidak-bisa-submit-sitemap.png)

## Mencari Solusi
Pertama saya mencoba membuka _Google Search Console_ saya dan coba melakukan _submit sitemap_ dan ternyata bisa. Karena saya ngeblog menggunakan Hugo dan tidak pernah mengalami kendala, saya berasumsi mungkin ada bug di blogger atau template yang digunakan. berikutnya saya mencoba membuat blog baru dengan custom domain dan tema premium yang terbarukan, untuk memastikan kebenaran permasalahan itu. Dan saat mencoba ternyata benar, saat melakukan _submit sitemap_ terdapat notifikasi "_Couldn't Fetch_".

![Tidak dapat mengambil peta situs](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgqASpm3s2v5obx4x-GT8B6x2WDTby6V2HQ7zDu_MNdyK2OvuNrSoSMrNC01kDEyZtifJN12raqfrUpC5MLk7ObaLjhSZsXH4HaBRTVAvyNFXD1uA7P7vp37Nz-3P0yaJHxC6ruOGkg31GCwe58hgmVLHV552KiS5ddkiW3NSrX2bEKg2yQf9hJGY_m6YBH/s902/sitemap-eror.png)

Saya mencoba utak-atik submit dengan cara berbeda, tapi hasilnya tetap nihil. Karena tidak berhasil, kemudian saya mencoba _browsing_ cara mengatasi hal tersebut. Tapi diantara banyak cara yang dilakukan, hasilnya tetap tidak membuahkan hasil.

Sampai akhirnya saya membaca dokumen-dokumen dan forum dari situs Google terkait peta situs. Ternyata dari pendapat para ahli memang terdapat bug di Google Bot, dan disarankan menungggu Google Bot melakukan Crawl sendiri ke situs kita.

## Coba Cara Lain
Dirasa tidak membuahkan hasil, saya teringat sebuah tutorial untuk membuat halaman sitemap otomatis di blogger dengan cara yang mirip dalam menerapkan pengambilan _rss feed_ yang kemudian saya terapkan untuk melakukan submit sitemap lagi.

Jika pada umumnya _submit sitemap_ di Google Search Console dengan mengetikkan

{{< highlight html >}}

https://namadomain.com/sitemap.xml
{{< /highlight >}}

Saya ganti cara dengan mengetikkan

{{< highlight html >}}

https://domainanda.com/sitemap.xml?redirect=false&amp;start-index=1&amp;max-results=500
{{< /highlight >}}

Dan Viola... berhasil 😅

![Sitemap berhasil disubmit](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgY-bqMikqgVLL_k9i7gQR4oTNsKXGoeU0Sh7bXJMiBwESmMA45PypyqPe-r3TT1zIwOGJ21RahxpfQLahsI85zgilwHEXAjiwRlBG0cJJ445g7ZkKxfGRr6-q1MmPFwtfalU_wC0y4LZ4_XgBd63WJX6rXvrePb3gfHF_nWAHmX0Gkiz9QazbcQ4tj2afV/s914/sitemap-berhasil.png)

Peringatan pada sitemap "Couldn't Fetch" sudah tidak muncul, berganti dengan tulisan "Success". Yang berarti sitemap sudah berhasil disubmit ke Google Bot agar di Crawl.

Yah mungkin ini alternatif cara yang bisa dicoba untuk submit sitemap sementara waktu sampai bug Google Bot benar-benar diperbaiki. Atau jika ada cara lain bisa coba share dikomentar.