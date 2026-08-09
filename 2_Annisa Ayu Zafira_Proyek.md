# Integrasi Network Pharmacology dan Molecular Docking Senyawa Bioaktif Berberine terhadap Protein Target PPARG pada Aterosklerosis

## Pendahuluan
Aterosklerosis merupakan salah satu penyakit kardiovaskular yang berkaitan dengan proses inflamasi dan gangguan metabolisme lipid pada pembuluh darah. Perkembangan aterosklerosis melibatkan berbagai protein dan jalur biologis sehingga mekanismenya tidak hanya bergantung pada satu target saja. Salah satu pendekatan yang dapat digunakan untuk mempelajari hubungan tersebut adalah network pharmacology. Pendekatan ini dapat menunjukkan hubungan antara senyawa aktif, target protein, dan pathway yang berperan dalam suatu penyakit. Scutellaiae Radix-Coptidis Rhizoma merupakan kombinasi tanaman obat tradisional yang memiliki senyawa bioaktif seperti qurcetin, wogonin, baicalein, beta-sitosterol, dan berberine. Senyawa-senyawa tersebut memiliki aktivitas yang berkaitan dengan inflamasi dan metabolisme lipid sehingga berpotensi memberikan efek terhadap penyakit aterosklerosis (Ji et al., 2023).

Laporan ini bertujuan untuk menganalisis interaksi antara berberine dan PPARG setelah dilakukan network pharmacology dan molecular docking. Dalam analisis ini protein PPARG yang digunakan memiliki PDB ID: 6TSG, sedangkan berberine digunakan sebagai ligan. Analisis dilakukan untuk memperoleh nilai binding affinity serta mengetahui jenis interaksi yang terbentuk antara berberine dan residu asam amino pada PPARG.

## Metode
### Analisis Network Pharmacology

Analisis network pharmacology dilakukan untuk mengetahui hubungan antara senyawa aktif Scutellaiae Radix-Coptidis Rhizoma, target protein, dan pathway yang berkaitan dengan aterosklerosis, Senyawa aktif yang digunakan meliputi qurcetin, wogonin, baicalein, beta-sitosterol, dan berberine yang berdasarkan literatur. Target dari masing-masing senyawa diidentifikasi menggunakan PubChem dan Swiss target Prediction, sedangkan target yang berkaitan dengan aterosklerosis diperoleh dari basis data penyakit OMIM. Selanjutnya, dilakukan analisis irisan antara target senyawa dan target aterosklerosis dengan Venny 2.1.0 untuk memperoleh target yang berpotensi berhubungan dengan mekanisme kerja senyawa aktif terhadap penyakit.

Target hasil irisan kemudian dianalisis menggunakan STRING untuk mengetahui hubungan protein-protein dalam jarinagn Protein-Protein Interaction (PPI). Hasil jaringan PPI selanjutnya divisualisasikan menggunakan Cytoscape. Analisis jaringan dilakukan untuk melihat tingkat keterhubungan masing-masing protein menggunakan metode Degree pada Cytoscape melalui aplikasi cytoHubba. Selain itu, dilakukan analisis Gene Ontology (GO) dan Kyto Encyclopedia of Genes and Genomes (KEGG) untuk mengetahui fungsi biologis dan pathway yang berkaitan dengan target hasil irisan. Berdasarkan hasil jaringan senyawa-target-pathway, PPARG dipilih sebagai salah satu target untuk dianalisis lebih lanjut menggunakan molecular docking karena memiliki hubungan dengan senyawa berberine dan PPAR signaling pathway.

### Preparasi Protein target
Preparasi target yang digunakan dalam molecular docking adalah Peroxisome Proliferator-Activated Receptor Gamma (PPARG) dengan PDB ID 6TSG. Struktur 3D protein diperoleh dari RSCB Protein Data Bank (RSCB PDB). Struktur tersebut memiliki resolusi sebesar 2,98 Å. Protein kemudian dipreparasi menggunakan BIOVIA Discovery Studio sebelum digunakan dalam proses molecular docking.

Preparasi protein dilakukan dengan menghilangkan molekul air yang terdapat pada struktur protein serta menghapus ligan atau molekul ko-kristal yang tidak digunakan dalam proses docking. Selanjutnya, atom hidrogen polar ditambahkan pada struktur untuk membantu pembentukan interaksi antara protein dan ligan. Struktur protein hasil preparasi kemudian akan disimpan dan dikonversi ke format yang sesuai untuk nantinya digunakan dalam perangkat lunak PyRx 0.8.

### Preparasi Ligan
Ligan yang digunakan dalam analisis ini adalah berberine. Struktur 3D berberine diperoleh dari PubChem dalam bentuk 3D conformer. Berberine memiliki PubChem CID 2353. Struktur ligan kemudian digunakan sebagai molekul uji dalam proses molecular docking terhadap protein PPARG.

Struktur berberine yang telah diperoleh disiapkan dalam format yang dapat digunakan pada PyRx. Ligan kemudian diimpor bersama protein PPARG hasil preparasi untuk dilakukan proses molecular docking. Penggunaan struktur 3D bertujuan agar konfigurasi spesial ligan dapat digunakan dalam prediksi interaksi dengan binding site protein.

### Penentuan Binding Site dan Grid Box
Penentuan lokasi binding site dilakukan berdasarkan prediksi pocket pada struktur protein PPARG menggunakan BIOVIA Discovery Studio. Koordinat pusat atau center dari pocket digunakan sebagai dasar untuk menentukan posisi grid box pada PyRx. Koordinat yang diperoleh dari BOIVIA Discovery Studio kemudian dimasukkan ke dalam pengaturan grid pada PyRx.

| Parameter  | Biovia |  PyRx |
| ----------|------------|-------------|
| Center X | -4.340545     |  -4.7168  |
| Center Y   | -2.257500    |  -2.3785  |
 Center Z   | -20.282136   |  -20.8548  |

 **Tabel 1. Koordinat center binding site PPARG**  

 Terdapat sedikit perbedaan antara nilai koordinat yang diperoleh dari BIOVIA Discovery Studio dan nilai yang ditampilkan pada PyRx. Pervedaan tersebut terjadi karena PyRx melakukan penyesuaian nilai koordinat ketika posisi grid box diatur. Koordinat hasil penyesuaian kemudian digunakan sebagai acuan dalam proses docking.

 ### Molecular Docking
 Molecular docking dilakukan menggunakan PyRx 0.8 dengan AutoDock Vina sebagai docking engine. Struktur protein PPARG dan ligan berberine yang telah dipreparasi dimasukkan ke dalam PyRx. Grid box kemudian diatur berdasarkan koordinat binding site yang telah diperoleh sebelumnya. Proses docking dilakukan untuk memperoleh beberapa kemungkinan pose atau mode ikatan berberine pada protein PPARG.

 Hasil docking menghasilkan nilai binding affinity, RMSD Lower Bound (RMSD/LB), dan RMSD Upper Bound (RMSD/UB) untuk setiap pose. Binding affinity digunakan sebagai parameter utama untuk membandingkan kecenderungan afinitas interaksi antara berberine dan PPARG. Nilai binding affinity yeng lebih negatif menunjukkan prediksi interaksi yang lebih menguntungkan secara energi dibandingkan nilai yang lebih tinggi. Pose dengan nilai binding affinity paling negatif dipilih sebagai pose terbaik untuk analisis interaksi lebih lanjut.

 ### Analisis Interaksi Protein-Ligan
Hasil molecular docking kemudian divisualisasikan menggunakan BIOVIA Discovery Studio untuk mengetahui interaksi antara berberine dan residu asam amino pada PPARG. Analisis dilakukan menggunakan visualisasi interaksi 2D untuk mengidentifikasi jenis interaksi non-kovalen yang terbentuk.

Jenis interaksi yang diamati meliputi van der Waals, hydrogen bond, Alkyl, Pi-Sulfur, dan interaksi lain. Selain interaksi yang menguntungkan, ada keberadaan unfavorable bump yang tercatat karena dapat menunjukkan adanya kedekatan atom yang kurang menguntungkan antara ligan dan residu protein. Hasil visualisasi kemudian digunakan untuk mendukung interpretasi nilai binding affinity dan menjelaskan karakteristik interaksi berberine dengan PPARG.

## Hasil dan Interpretasi
### Hasil Analisis Network Pharmacology
Hasil analisis network pharmacology menunjukkan adanya 14 gen irisan antara target penyakit aterosklerosis dan target senyawa aktif Scutellariae Radix-Coptidis Rhizoma. Diantaranya, adalah CNR2, PDE1A, PPARG, PDE4D, ADRA1B, PPARD, ESR1, NPC1L1, FABP4, ALOX5, F2, NR1H3, MMP3,dan MMP12. Selanjutnya, gen hasil irisan ini digunakan sebagai dasar dalam penyusunan jaringan PPI untuk mengidentifikasi protein yang memiliki peranan sentral dalam jaringan biologis.

| Name  | Score |
| ------------- |:-------------:|
| IL6    | 78   |
| TNF     | 71     |
| INS      | 69     |
| EGFR     | 69     |
| ILIB    | 65     |
| SRC      | 64     |
| CTNNB1     | 64     |
| AKT1      | 62     |
| ALB      | 57     |
| TLR4      | 50     |
| HIF1A      | 49     |
| ESR1      | 49     |
| NFKB1      | 49     |
| EP300      | 48     |
| SIRT1    | 46     |
| JUN      | 45     |
| PPARG      | 44     |
| APOB      | 42     |
| IL10     | 42     |
| RELA      | 40     |

**Tabel 2. Nilai degree dan Score**

Dalam tabel yang telah di olah menggunakan cytoHubba dengan menggunakan metode Degree, lima protein dengan nilai tertinggi adalah IL6 (78), TNF (71), INS (69), EGFR (69), dan IL1B (65). Protein-protein tersebut diperkirakan berperan sebagai hub gene karena memiliki konektivitas paling tinggi dibandingkan protein lainnya. Tingginya nilai degree menunjukkan bahwa protein tersebut berpotensi menjadi regulator utama dalam proses inflamasi, regulasi metabolisme, proliferasi sel, serta respons imun yang berkontribusi terhadap perkembangan aterosklerosis.

![Jaringan Protein-Protein Interaction (PPI) dengan STRING.](/jaringan.png "Jaringan Protein-Protein Interaction (PPI) dengan STRING.")

**Gambar 1. Jaringan Protein-Protein Interaction (PPI) dengan STRING**

Jaringan Protein-Protein Interaction (PPI) menunjukkan hubungan antarprotein hasil irisan yang diprediksi saling berinteraksi dalam mekanisme biologis aterosklerosis. Berdasarkan hasil analisis menggunakan STRING, sebagian besar protein target saling terhubung membentuk jaringan interaksi kompleks. Hubungan tersebut menunjukkan bahwa mekanisme perkembangan aterosklerosis tidak dikendalikan oleh satu protein saja, melainkan melibatkan berbagai protein yang saling memengaruhi. 

![Visualisasi jaringan interaksi senyawa-target-pathway.](/visualisasi.png "Visualisasi jaringan interaksi senyawa-target-pathway.")

**Gambar 2. Visualisasi jaringan interaksi senyawa-target-pathway**

Berdasarkan visualisasi jaringan, senyawa β-sitosterol, berberine, dan wogonin berinteraksi dengan beberapa target protein yaitu PPARA, FABP1, FABP5, NR1H3, ESR1. Target-target tersebut terhubungan dengan PPAR signaling pathway. Hubungan antara senyawa aktif, target protein, dan jalur biologis tersebut menunjukkan bahwa efek terapeutik kombinasi tanaman ini memungkinkan diperoleh melalui modulasi berbagai proses biologis yang saling berkaitan.

![Analysis Gene Ontology.](/go.png "Analysis Gene Ontology.")

![Analisis KEGG.](/kegg.png "Analisis KEGG.")

**Gambar 3. Hasil enrichment analysis Gene Ontology dan KEGG dalam STRING**

Analisis Gene Ontology kategori Biological Process menunjukkan bahwa target hasil irisan terutama terlibat dalam proses adenylate cyclase-activating adrenergic receptor signaling pathway, adenylate cyclase-activating G protein-coupled receptor signaling pathway, blood circulation, cellular response to chemical stimulus, dan cellular response to lipid. Proses-proses tersebut berkaitan erat dengan mekanisme inflamasi, stres oksidatif, regulasi apoptosis, maupun metabolisme lipid yang diketahui berperan dalam perkembangan aterosklerosis.

Pada kategori Molecular Function, target menunjukkan pengayaan pada fungsi lipid binding, long-chain fatty acid binding, nuclear receptor activity, metal ion binding, dan 3`,5`-cyclic—MP phospodiesterase activity. Hasil ini mengindikasikan bahwa protein target memiliki peran penting dalam pengikatan lipid, pengaturan metabolisme asam lemak, serta regulasi transkripsi melalui reseptor nuklir yang berhubungan dengan homeostasis lipid.

Sementara itu, analisis KEGG pathway menunjukkan bahwa target hasil irisan terutama terlibat dalam PPAR signaling pathway (hsa03320). Jalur ini merupakan regulator utama metabolisme lipid yang mengendalikan transport asam lemak, oksidasi asam lemak, diferensiasi adiposit, dan homeostasis energi. Berdasarkan visualisasi KEGG, beberapa target seperti FABP1, FABP3, APOA1, dan APOA2 berpartisipasi langsung dalam jalur tersebut. Aktivasi jalur PPAR diperkirakan membantu memperbaiki  metabolisme lipid, meningkatkan transport dan oksidasi asam lemak, serta mengurangi akumulasi lipid yang berkontribusi terhadap pembentukan plak  aterosklerosis. Hail ini memperkuat dugaan bahwa senyawa aktif Scutellariae Radix-Coptidis Rhizoma bekerja melalui mekanisme multi-target dan multi-pathway dalam menghambat perkembangan aterosklerosis.

### Hasil Analisis Molecular Docking
Protein yang digunakan dalam molecular docking adalah PPARG. Sebelum digunakan dalam proses docking, protein dipreparasi menggunakan BIOVIA Discovery Studio. Preparasi dilakukan dnegan menghilangkan molekul air dan ligan ko-kristal yang terdapat pada struktur protein. Selanjutnya, atom hidrogen polar ditambahkan sebelum digunakan dalam proses molecular docking.

![struktur.](/struktur.png "struktur.")

**Gambar 4. Struktur Protein PPARG akhir dalam Biovia Discovery Studio**  

Selanjutnya, imporan struktur protein yang terbaru dimasukkan ke dalam PyRx dengan conformer berberine 3D dalam format PDB. Keduanya, dijalankan dan menghasilkan sebuah ikatan. Setelah dilakukan penentuan grid dan dilanjutkan proses analisis akan menghasilkan nilai binding affinity, RMSD Lower Bound, dan RMSD Upper Bound.

 | Ligand | Binding Affinity | RMSD/LB |RMSD/UB|
| ----------|------------|-------------|-------------|
| 6TSG_prep_berberine | -9.5     | 0.0  |0.0 |
| 6TSG_prep_berberine | -9.4     | 1.375  |7.7668 |
| 6TSG_prep_berberine | -8.0     | 4.005  |6.091 |
| 6TSG_prep_berberine | -7.4     | 4.637  |7.795 |
| 6TSG_prep_berberine | -7.4     | 5.974  |8.928 |
| 6TSG_prep_berberine | -7.0     | 15.289  |17.232 |
| 6TSG_prep_berberine | -6.7     | 13.176  |15.234 |
| 6TSG_prep_berberine | -6.7     | 7.206  |9.24 |

**Tabel 3. Hasil Molecular Docking Wogonin terhadap PPARG**

Hasil tersebut menghasilkan 8 mode dari mode 0-7 dengan nilai binding affinity yang berbeda. Model terbaik ditentukan berdasarkan nilai energi ikatan paling negatif karena menunjukkan kompleks protein-ligan yang paling stabil. Dalam tabel tersebut, model terbaik menunjukkan nilai binding affinity sebesar -9.5 dengan nilai RMSD adalah 0.0. Nilai tersebut mengindikasikan bahwa berberine memiliki kemampuan berikatan secara spontan dengan protein PPARG.

### Hasil Analisis Interaksi Berberine dengan PPARG
Hasil terbaik yang diperoleh dari hasil molecular docking selanjutnya divisualisisasikan menggunakan BIOVIA Discovery Studi dalam bentuk 2D.

![visligan.](/visligan.png "visligan.")

**Gambar 5. Visualisasi Protein-Ligan dengan Biovia Discovery Studio**  

Berdasarkan hasil visualisasi interaksi 2D menggunakan Biovia Discovery Studio pada pose terbaik dengan mode 0 dengan binding affinity -9.5 kcal/mol, kompleks PPARG – Berberine menunjukkan beberapa interaksi non-kovalen, yaitu:
1. Interaksi van der Waals terbentuk pada residu asam amino ASN A:253, GLY A:258 dan ASP A:260. Interaksi ini menunjukkan adanya kontak antara berberine dengan residu pada kantong ikatan PPARG dan dapat membantu mempertahankan posisi ligan melalui gaya tarik intermolekuler yang relatif lemah.
2. Interaksi Pi-Sulfur juga terdeteksi pada kompleks PPARG-Berberine. Interaksi ini terjadi antara sistem π pada struktur cincin berberine dengan bagian sulfur dari residu yang berinteraksi. Interaksi tersebut dapat berkontribusi terhadap pengenalan dan kestabilan posisi berberine di dalam kantong ikatan PPARG.
3. Interaksi Alkyl terlihat pada struktur kompleks PPARG-Berberine. Interaksi ini menunjukkan adanya kontak hidrofobik antara bagian struktur berberine dengan gugus alkil pada residu asam amino di sekitar binding site. 
4. Selain interaksi yang mendukung kompleks, terdapat Unfavorable Bump pada residu MET 1:257. Interaksi ini terjadi sedikit tumpang tindih atau jarak atom terlalu dekat antara berberine dan residu. Kondisi ini kurang menguntungkan dan dapat menjadi faktor yang berpengaruh pada kestabilan.

## Kesimpulan
Berdasarkan analisis network pharmacology dan molecular docking, berberine memiliki hubungan dengan PPARG yang terlibat dalam PPAR signaling pathway pada aterosklerosis. Hasil docking menunjukkan binding affinity terbaik sebesar -9,7 kcal/mol dengan RMSD 0,0. Visualisasi menunjukkan interaksi van der Waals, Pi-Sulfur, dan Alky, serta unfavorable bump pada MET A:257. Hasil tersebut menunjukkan potensi interaksi berberine dengan PPARG dan mendukung keterlibatannya dalam regulasi metabolisme lipid. Namun, hasil ini masih bersifat in silico sehingga diperlukan penelitian eksprerimental untuk memastikan aktivitas dan mekanisme berberine terhadap PPARG.

## Referensi
Ji, L., Song, T., Ge, C., Wu, Q., Ma, L., Chen, X., Chen, T., Chen, Q., Chen, Z., & Chen, W. (2023). Identification of bioactive compounds and potential mechanisms of Scutellariae Radix-Coptidis Rhizoma in the treatment of atherosclerosis by integrating network pharmacology and experimental validation. Biomedicine & Pharmacotherapy, 165, 115210. https://doi.org/10.1016/j.biopha.2023.115210
