# **EN: Optimization of Unrelated Parallel Machines using Genetic Algorithm**

## **Project Description**
This project addresses the **scheduling and optimization problem in unrelated parallel machines** using a genetic algorithm. The objective is to minimize the total processing time (makespan) and simulate this process using MATLAB. In this study, the job scheduling problem for machines with varying efficiency levels is solved, aiming to achieve the best solution based on fitness values.

The project involves crossover and mutation operations that ensure job IDs remain unique and genetic diversity is preserved. Additionally, an elitism strategy is employed to enhance the performance of the genetic algorithm.

## **Methods Used**

### **1. Genetic Algorithm**
The genetic algorithm serves as the primary solution method in this project. The following components constitute the core structure of the genetic algorithm:

- **Representation Matrix:** The solution is represented as a two-row matrix. The first row contains the job sequence (permutation), while the second row represents machine IDs as integers.

  ![Representation Matrix](images/Representation%20Matrix.PNG)

- **Data Source:** The data is sourced from the paper by Vallada and Ruiz (2011), titled *"A genetic algorithm for the unrelated parallel machine scheduling problem with sequence-dependent setup times."* This data includes the job processing times and setup times between jobs on different machines.

### **2. Data Processing**
- **`p` Variable:** This matrix represents the processing times of specific jobs on each machine. Each row corresponds to a machine, and each column represents a job. For example, `p(i, j)` denotes the time taken by machine `i` to complete job `j`.

  ![`p` Variable](images/p%20Variable.PNG)
  
- **`s` Variable:** This cell array represents the setup times between jobs on machines. Each cell contains a matrix for a specific machine, where rows and columns correspond to job IDs. The value `s{i}(j, k)` indicates the setup time required for machine `i` to switch from job `j` to job `k`.

  ![`s` Variable](images/s%20Variable.PNG)

### **3. Crossover and Mutation**
- **Crossover:** Single-point crossover is applied. Single-point crossover is used for machine IDs, while OX (Order Crossover) is employed for job IDs to prevent duplication of job IDs.
  
- **Mutation:** A random mutation method is used for machine IDs, while a swap method that preserves uniqueness is used for job IDs.

### **4. Elitism**
Elitism strategy is used to ensure that the best solutions are not lost during the genetic algorithm process. In this project, the best chromosomes are preserved at the end of each iteration and are used in the formation of the new population.

## **Project Files**

- **`main.m`**: The main MATLAB script containing all the steps of the genetic algorithm.
- **`Eachs_epochs_best_result.xlsx`**: Excel file where the results of the algorithm are saved. The best chromosome information at the end of each iteration is written here.

## **Usage Guide**

1. **MATLAB Setup:** Ensure that MATLAB is installed.
2. **Running the Code:** Run the `main.m` file to start the genetic algorithm.
3. **Data Input:** The data is automatically loaded from the `DatasetSamples` file.
4. **Analyzing Results:** The results are saved in the `Eachs_epochs_best_result.xlsx` file, where the best solutions can be reviewed at the end of each iteration.

## **References**
- Vallada, E., Ruiz, R., 2011. *A genetic algorithm for the unrelated parallel machine scheduling problem with sequence-dependent setup times*. European J. Oper. Res. 211 (3), 612–622.


---

# **TR: Genetik Algoritma Kullanarak İlişkisiz Paralel Makinelerin Optimizasyonu**

## **Proje Açıklaması**
Bu proje, **ilişkisiz paralel makinelerdeki zamanlama ve optimizasyon sorununu** genetik algoritma kullanarak ele almaktadır. Amaç, toplam işlem süresini (makespan) en aza indirmek ve bu süreci MATLAB kullanarak simüle etmektir. Bu çalışmada, verimlilik düzeyleri farklı olan makineler için iş zamanlama problemi çözülmüş ve uygunluk değerlerine dayalı olarak en iyi çözüm elde edilmeye çalışılmıştır.

Proje, iş kimliklerinin benzersiz kalmasını ve genetik çeşitliliğin korunmasını sağlamak için çaprazlama ve mutasyon işlemlerini içermektedir. Ayrıca, genetik algoritmanın performansını artırmak için elitizm stratejisi uygulanmaktadır.

## **Kullanılan Yöntemler**

### **1. Genetik Algoritma**
Genetik algoritma, bu projede birincil çözüm yöntemi olarak kullanılmıştır. Genetik algoritmanın temel yapısını oluşturan bileşenler şunlardır:

- **Temsil Matrisi:** Çözüm, iki satırlı bir matris olarak temsil edilir. İlk satır iş sırasını (permütasyon) içerirken, ikinci satır makine kimliklerini tam sayı olarak temsil eder.

  ![Temsil Matrisi](images/Representation%20Matrix.PNG)

- **Veri Kaynağı:** Veriler, Vallada ve Ruiz (2011) tarafından yazılan *"A genetic algorithm for the unrelated parallel machine scheduling problem with sequence-dependent setup times"* başlıklı makaleden alınmıştır. Bu veriler, farklı makinelerde işler arasındaki işlem süreleri ve kurulum sürelerini içermektedir.

### **2. Veri İşleme**
- **`p` Değişkeni:** Bu matris, belirli işlerin her bir makinedeki işlem sürelerini temsil eder. Her satır bir makineye, her sütun ise bir işi temsil eder. Örneğin, `p(i, j)` makine `i`nin iş `j`yi tamamlama süresini belirtir.

  ![`p` Değişkeni](images/p%20Variable.PNG)
  
- **`s` Değişkeni:** Bu hücre dizisi, makinelerde işler arasındaki kurulum sürelerini temsil eder. Her hücre, belirli bir makine için bir matris içerir ve satırlar ve sütunlar iş kimliklerine karşılık gelir. `s{i}(j, k)` değeri, makine `i`nin iş `j`den iş `k`ye geçmesi için gereken kurulum süresini gösterir.

  ![`s` Değişkeni](images/s%20Variable.PNG)

### **3. Çaprazlama ve Mutasyon**
- **Çaprazlama:** Tek noktalı çaprazlama uygulanır. Makine kimlikleri için tek noktalı çaprazlama kullanılırken, iş kimliklerinin tekrarını önlemek için OX (Sıra Çaprazlaması) kullanılır.
  
- **Mutasyon:** Makine kimlikleri için rastgele mutasyon yöntemi kullanılırken, benzersizliği koruyan bir değiştirme yöntemi iş kimlikleri için kullanılır.

### **4. Elitizm**
Elitizm stratejisi, genetik algoritma sürecinde en iyi çözümlerin kaybolmamasını sağlamak için kullanılır. Bu projede, her yinelemenin sonunda en iyi kromozomlar korunur ve yeni popülasyonun oluşumunda kullanılır.

## **Proje Dosyaları**

- **`main.m`**: Genetik algoritmanın tüm adımlarını içeren ana MATLAB dosyası.
- **`Eachs_epochs_best_result.xlsx`**: Algoritmanın sonuçlarının kaydedildiği Excel dosyası. Her yinelemenin sonunda en iyi kromozom bilgileri buraya yazılır.

## **Kullanım Kılavuzu**

1. **MATLAB Kurulumu:** MATLAB'in yüklü olduğundan emin olun.
2. **Kodun Çalıştırılması:** Genetik algoritmayı başlatmak için `main.m` dosyasını çalıştırın.
3. **Veri Girişi:** Veriler, `DatasetSamples` dosyasından otomatik olarak yüklenir.
4. **Sonuçların Analizi:** Sonuçlar `Eachs_epochs_best_result.xlsx` dosyasına kaydedilir ve her yinelemenin sonunda en iyi çözümler incelenebilir.

## **Referanslar**
- Vallada, E., Ruiz, R., 2011. *A genetic algorithm for the unrelated parallel machine scheduling problem with sequence-dependent setup times*. European J. Oper. Res. 211 (3), 612–622.
