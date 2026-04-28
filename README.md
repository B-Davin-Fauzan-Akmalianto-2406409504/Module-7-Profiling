## Module 7 Notes

### Disclaimer
SEED SIZE saya ganti dari 20k menjadi 10k.

### Test Result 1 JMeter
![test_result_1_jmeter.png](images/test_result_1_jmeter.png)
### Test Result 2 JMeter
![test2jmeter.png](images/test2jmeter.png)
### Test Result 3 JMeter
![testGPAjmeter.png](images/testGPAjmeter.png)
### Test Result 1 CMD
![test1cmd.png](images/test1cmd.png)
### Test Result 2 CMD
![test2cmd.png](images/test2cmd.png)
### Test Result 3 CMD
![testGPAcmd.png](images/testGPAcmd.png)


## After Optimizing

### Test Result 1 JMeter
![img.png](images/testResult1Optimized.png)

### Test Result 2 JMeter
![img.png](images/testResult2Optimized.png)

### Test Result 3 JMeter
![img.png](images/testResult3Optimized.png)

## Notes
Dari kedua segmen, bisa terlihat bahwa perbedaan antara sebelum dan sesudah optimize begitu jauh.
Hal ini terjadi karena pada kode sebelum optimize, kode melakukan fetching ke database setiap iterasi, yang tentu memakan banyak waktu.
Setelah di optimize, kode melakukan query secara kolektif/barengan, sehingga waktu dapat dipangkas sangat jauh.

## Reflection

### 1. "What is the difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance?"

Ketika kita menggunakan profiler IntelliJ, kita bisa melihat CPU time yang dipakai oleh masing-masing fungsi yang terlibat, sehingga bisa pinpoint dimana fungsi yang meng-bottleneck waktu.
Ketika performance testing menggunakan JMeter, kita bisa melihat total runtime yang dijalankan oleh masing-masing thread. 

### 2. "How does the profiling process help you in identifying and understanding the weak points in your application?"

Di profiling, kita bisa melihat proses (fungsi) yang berjalan lambat sehingga bisa langsung meninjau fungsi tersebut dan segera mengoptimizenya.

### 3. "Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?"

Ya, seperti yang disebutkan sebelumnya.

### 4. "What are the main challenges you face when conducting performance testing and profiling, and how do you overcome these challenges?"

Main challengenya mungkin adalah menunggu agar proses selesai dilaksanakan, karena untuk tiap test tidak instan sehingga perlu kesabaran.

### 5. "What are the main benefits you gain from using IntelliJ Profiler for profiling your application code?"

Main benefitnya bisa lihat dengan precise mana fungsi yang membebani hasil akhir runtime.

### 6. "How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?"

Sebenarnya karena IntelliJ bersifat internal dan JMeter bersifat external layaknya user yang sedang memakai, memang seharusnya yang dari JMeter inherently lebih lambat dibanding melihat dari IntelliJ. Oleh karena itu, mungkin aku lebih melihat JMeter sebagai baseline. Jika di JMeter terlihat lambat, ya berarti memang lambat, dan aku harus ke profiler di IntelliJ agar mengetahui mana proses yang membuat lambat. Jika di JMeter sudah cepat, ya berarti seharusnya sudah aman.

### 7. "What strategies do you implement in optimizing application code after analyzing results from performance testing and profiling? How do you ensure the changes you make do not affect the application's functionality?"

Sudah sempat saya mention di poin 6, basically lihat JMeter sebagai base lalu lanjut ke profiling agar mengetahui fungsi mana yang menjadi beban.
Kemudian, untuk mengecek fungsionalitas bisa menggunakan unit testing.