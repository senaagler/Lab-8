# Lab-8
package lab_2;

import java.util.ArrayList;

class Ogrenci {
    private static int ogrenciSayisi = 0;
    private String ad;
    private int sinif;
    private ArrayList<Ders> derslistesi;

    public Ogrenci() {
        ogrenciSayisi++;
        this.ad = "Sena";
        this.sinif = 3;
        derslistesi = new ArrayList<>();
    }

    public Ogrenci(String ad, ArrayList<Ders> derslistesi) {
        ogrenciSayisi++;
        this.ad = ad;
        this.sinif = 2;
        this.derslistesi = derslistesi;
    }

    public Ogrenci(String ad, int sinif, ArrayList<Ders> derslistesi) {
        ogrenciSayisi++;
        this.ad = ad;
        this.sinif = sinif;
        this.derslistesi = derslistesi;
    }

    public void OgrenciBilgisiYaz() {
        System.out.println("Ad: " + ad);
        System.out.println("Sinif: " + sinif);
        System.out.println("Ogrenci Sayisi: " + ogrenciSayisi);
        System.out.println("Aldigi Ders Sayisi: " + derslistesi.size());
    }

    public void OgrenciDersBilgiYaz() {
        System.out.println("\n" + ad + " ogrencisinin aldigi dersler:");
        for (Ders ders : derslistesi) {
            ders.DersBilgisiYaz();
        }
    }

    public void dersEkle(Ders ders) {
        derslistesi.add(ders);
        ders.DersBilgisiYaz();
    }
}

class Ders {
    private static int dersSayisi = 0;
    private String ad;
    private int sinif;
    private String hoca;

    public Ders() {
        dersSayisi++;
        this.ad = "";
        this.sinif = 0;
        this.hoca = "";
    }

    public Ders(String ad) {
        dersSayisi++;
        this.ad = ad;
        this.sinif = 0;
        this.hoca = "";
    }

    public Ders(String ad, int sinif, String hoca) {
        dersSayisi++;
        this.ad = ad;
        this.sinif = sinif;
        this.hoca = hoca;
    }

    public void DersBilgisiYaz() {
        System.out.println("Ders Adi: " + ad);
        System.out.println("Sinif: " + sinif);
        System.out.println("Hoca: " + hoca);
    }

    public static void DersSayiBilgisiYaz() {
        System.out.println("Toplam Ders Sayisi: " + dersSayisi);
    }
}

public class Lab6 {
    public static void main(String[] args) {
        Ogrenci ogrenci1 = new Ogrenci();
        ogrenci1.OgrenciBilgisiYaz();

        	
        ArrayList<Ders> dersListesi2 = new ArrayList<>();
        dersListesi2.add(new Ders("nesneye yönelik programlama", 3, "ibrahim hoca"));
        
        Ogrenci ogrenci2 = new Ogrenci("Ali", dersListesi2);
        ogrenci2.OgrenciBilgisiYaz();

        ArrayList<Ders> dersListesi = new ArrayList<>();
        dersListesi.add(new Ders("Matematik", 1, "yılmaz hoca"));
        dersListesi.add(new Ders("Fizik", 2, "emin hoca"));

        Ogrenci ogrenci3 = new Ogrenci("Ayse", 2, dersListesi);
        ogrenci3.OgrenciBilgisiYaz();

        Ders ders1 = new Ders("Kimya", 1, "ibrahim hoca");
        ogrenci3.dersEkle(ders1);

        ogrenci2.OgrenciDersBilgiYaz();
        ogrenci3.OgrenciDersBilgiYaz();

        Ders.DersSayiBilgisiYaz();
    }
}
