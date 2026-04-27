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