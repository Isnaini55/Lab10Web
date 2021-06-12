# Lab10Web

# Praktikum 10
~~~
Nama  : Isnaini Rizkyana
NIM   : 311910254
Kelas : TI.19.C1
~~~

## Langkah-langkah Praktikum

## Buat folder baru dengan nama lab10_php_oop pada docroot webserver (htdocs)
![lab10_php_oop](https://user-images.githubusercontent.com/81541764/121777404-0bf7a000-cbbc-11eb-8b14-48269897b2b6.jpg)

## Buat file baru dengan nama mobil.php
~~~
<?php 
/**
 * Program sederhana pendefinisian class dan pemanggilan class
 **/

 class Mobil
 {
     private $warna;
     private $merk;
     private $harga;

     public function __construct()
     {
         $this->warna = "Biru";
         $this->merk = "BMW";
         $this->harga = "10000000";
     }

     public function gantiWarna ($warnaBaru)
     {
         $this->warna = $warnaBaru;
     }

     public function tampilWarna()
     {
         echo "Warna mobilnya : " . $this->warna;
     }
 }

//  membuat objek mmobil
$a = new Mobil();
$b = new Mobil();

// memangging objek
echo "<b>Mobil pertama</b><br>";
$a->tampilWarna();
echo "<br>Mobil pertama ganti warna<br>";
$a->gantiWarna("Merah");
$a->tampilWarna();

// memanggil objek
echo "<br><b>Mobil kedua</b><br>";
$b->gantiWarna("Hijau");
$b->tampilWarna();

?>
~~~
![mobil](https://user-images.githubusercontent.com/81541764/121750801-42d7a280-cb37-11eb-8ab9-31083e3820cc.JPG)

## Buat file baru dengan nama form.php
~~~
<?php 
/**
 * Nama Class : Form
 * Deskripsi : Class untuk membuat forminputan text sederhana
 */

 class Form
{
    private $fields = array();
    private $action;
    private $submit = "Submit Formm";
    private $jumField = 0;

    public function __construct($action, $submit)
    {
        $this->action = $action;
        $this->submit = $submit;
    }

    public function displayForm()
    {
        echo "<form action='".$this->action."' method='POST'>";
        echo '<table width="100%" border="0">';
        for ($j=0; $j<count($this->fields); $j++) {
            echo 
            "<tr>
                <td
                    align='right'>".$this->fields[$j]['label'].
                "</td>";
            echo 
                "<td>
                    <input type='text' name='".$this->fields[$j]['name']."'>
                </td>
            </tr>";
        }

    
        echo
        "<tr>
            <td colspan='2'>";
                "<input type='submit' value='".$this->submit."'>
            </td>
        </tr>";
        echo "</table>";
    }

    public function addField($name, $label)
    {
        $this->fields [$this->jumField]['name'] = $name;
        $this->fields [$this->jumField]['label'] = $label;
        $this->jumField ++;
    }
}
?>
~~~
![form](https://user-images.githubusercontent.com/81541764/121750986-90eca600-cb37-11eb-8cad-3f00de61ce4f.JPG)

## Buat file baru dengan nama form_input.php
~~~
<?php 
/**
 * Program pemanfaatan Program 10.2 untuk membuat form inputan sederhana.
 */

 include "form.php";

 echo "<html><head><title>Mahasiswa</title></head><body>";
 $form = new Form("","Input Form");
 $form->addField("txtnim", "Nim");
 $form->addField("txtnama", "Nama");
 $form->addField("txtalamat", "Alamat");
 echo "<h3>Silahkan isi form berikut ini : </h3>";
 $form->displayForm();
 echo "</body></html>"

?>
~~~
![form_input](https://user-images.githubusercontent.com/81541764/121751152-d315e780-cb37-11eb-90b7-4afd26c44b8b.JPG)
