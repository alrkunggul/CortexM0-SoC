# ARM Cortex-M0 SoC Project Development Documentation
## Project Report #1 (18 September 2025)
### Software Simulation
Telah dilakukan eksplorasi dan debugging agar bisa melakukan simulasi, telah diubah juga menggunakan GCC dari ARM GNU Toolchain. Namun, hasil yang didapatkan sama dan menghasilkan stack address bootrom yang salah sehingga diasumsikan bahwa perlu dilakukan penrubahan pada file startup_CMSDK_M0.s sehingga memiliki alamat stack address bootrom yang benar.

Disarankan oleh mas Ahmad untuk menggunakan file yang diberikan oleh beliau, dan simulasi menggunakan aplikasi Eclipse. Fila baru didapatkan pada hari Selasa, 16 September 2025, namun belum sempat dilakukan eksplorasi dan hari Rabu, 17 September 2025 baru saja diinstall aplikasi Eclipse pada server oleh Mas Michael, namun belum sempat dilakukan eksplorasi untuk menjalankan simulasi.
<img width="1917" height="1050" alt="image" src="https://github.com/user-attachments/assets/2a801224-9fb4-4387-a54c-a0bafb42bd4f" />

### Synthesis RTL
Synthesis sudah dapat dilakukan dengan sudah diimplementasikan SRAM yang dapat digunakan pada FPGA, namun masih terdapat critical warning pada constraint pinmap akibat masih terdapat kesalahan karena harus dilakukan pinmapping manual untuk FPGA ZCU104 (tidak disediakan oleh pihak ARM). Hasil Synthesis dapat dilihat pada gambar berikut.
<img width="1648" height="960" alt="image" src="https://github.com/user-attachments/assets/8d8fae94-c4be-49df-bcab-af459174ed16" />

### Meeting dengan SoCLabs
Dilakukan meeting dengan SoCLabs membahas bagaimana cara Setup environment dan menjalankan simulasi menggunakan file SoCLabs "NanoSoC Tech". Pada meeting kemerin juga menjelaskan apa saja yang terdapat didalamnya dan apa yang perlu dilakukan untuk bisa melakukan simulasi menggunakan NanoSoC.
![WhatsApp Image 2025-09-17 at 15 11 51_bc6a4dba](https://github.com/user-attachments/assets/ffe40110-2511-4a0e-a327-c133efd97722)


### Next Steps
1. Membenarkan pinmap untuk bisa Implementation dan generate bitstream untuk diupload ke FPGA ZCU104.
2. Mengeksplorasi ARM Cortex-M0 menggunakan Eclipse IDE.
3. Mengeksplorasi NanoSoC dan Mencoba Simulasi/Synthesis.
