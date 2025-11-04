# LatihanUKL-SoalMudahNo1-Ekspedisi-AzkyaRahma-XRPL2
Fungsi program ini menghitung total biaya pengiriman paket berdasarkan berat, jarak, dan volume. Volume >100 cm³ ditambah biaya ekstra. Tarif per kg sesuai jarak. Hasil ditampilkan dalam format Rupiah.
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.ukl_ara;

/**
 *
 * @author araaz
 */
import java.util.Scanner;
public class SOAL1_Ekspedisi {

    public static void main(String[] args) { 
        Scanner sc = new Scanner(System.in); 

        // --- BAGIAN INPUT --- //
        System.out.print("Masukkan berat paket (kg): ");
        double berat = sc.nextDouble(); // baca angka desimal (kg)

        System.out.print("Masukkan jarak tempuh (km): ");
        double jarak = sc.nextDouble(); // baca angka desimal (km)

        System.out.print("Masukkan panjang paket (cm): ");
        double panjang = sc.nextDouble();

        System.out.print("Masukkan lebar paket (cm): ");
        double lebar = sc.nextDouble();

        System.out.print("Masukkan tinggi paket (cm): ");
        double tinggi = sc.nextDouble();

        // --- BAGIAN PENGHITUNGAN ---
        double volume = panjang * lebar * tinggi; // rumus volume

        // Tentukan tarif per kg
        double tarifPerKg;
        if (jarak <= 10) {
            tarifPerKg = 4250;
        } else {
            tarifPerKg = 6000;
        }

        // Tentukan biaya tambahan volume
        double biayaTambahan;
        if (volume > 100) {
            biayaTambahan = 50000;
        } else {
            biayaTambahan = 0;
        }

        // Hitung total biaya
        double totalBiaya = (berat * tarifPerKg) + biayaTambahan;

        // --- BAGIAN OUTPUT ---
        System.out.println("\n=== HASIL PERHITUNGAN ===");
        System.out.println("Volume paket: " + volume + " cm^3");
        System.out.println("Tarif per kg: Rp" + tarifPerKg);
        System.out.println("Biaya tambahan volume: Rp" + biayaTambahan);
        System.out.println("Total biaya pengiriman: Rp" + totalBiaya);
    }
}

