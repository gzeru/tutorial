# CSS - mempercantik tampilan!

Blog yang kita buat masih terlihat monoton, bukan? Nah, sekarang waktunya untuk mempercantik tampilannya! Kita akan menggunakan CSS untuk itu.

## Apa itu CSS?

Cascading Style Sheets (CSS) adalah bahasa yang digunakan untuk mempresentasikan tampilan dan format situs web yang ditulis dalam bahasa markup (seperti HTML). Gunakan itu sebagai mekap untuk halaman web kita. ;)

Tapi kita tidak ingin melakukan itu (mempercantik) dari nol, bukan? Sekali lagi, kita akan menggunakan sesuatu yang telah pemrogram buat dan itu bisa digunakan secara gratis. Dan itu bisa mempersingkat waktu kita untuk membuat situs web, tepatnya blog.

## Mari kita gunakan Bootstrap!

Bootstrap adalah salah satu kerangka kerja untuk HTML dan CSS yang paling populer untuk mengembangkan situs web yang menarik: https://getbootstrap.com/

Bootstap ini ditulis oleh pemrogram yang bekerja untuk Twitter. Dan sekarang ini dikembangkan oleh sukarelawan dari seluruh dunia!

## Memasang Bootstrap

Untuk memasang Bootstap, bukan file berekstensi `.html` di editor kode dan tambahkan kode ini di dalam elemen HTML `<head>`

<head>
  </1>:</p> 
  
  <p>
    {% filename%} blog / templates / blog / post_list.html {% endfilename%}
  </p>
  
  <pre><code class="html">&lt;link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css"&gt; 
&lt;link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css"&gt;
</code></pre>
  
  <p>
    Kode di atas tidak akan ditambahkan ke dalam setiap file dalam proyek Anda. Ini hanyalah sebagai rujukan ke sebuah file yang ada di internet. Jadi, kembali lagi, buka situs web Anda dan <i>refresh</i> (muat ulang) halamanya. Inilah hasilnya!
  </p>
  
  <p>
    <img src="images/bootstrap1.png" alt="Gambar 14.1" />
  </p>
  
  <p>
    Terlihat lebih menarikkan!
  </p>
  
  <h2>
    File statis di Django
  </h2>
  
  <p>
    Akhirnya kita bisa lebih dekat dengan sesuatu yang dipanggil <strong>static files</strong> atau file statis. Statis file ini adalah semua hal yang berhubungan dengan CSS dan gambar. Ini berarti setiap pengguna atau mereka yang melakukan <i>request</i> akan disuguhkan tampilan yang sama.
  </p>
  
  <h3>
    Lokasi untuk menempatkan file statis di Django
  </h3>
  
  <p>
    Django sudah mengetahui di mana menemukan file statis ini. Sekarang kita perlu untuk menambahkan beberapa file statis ke dalam aplikasi kita, direktori <code>blog</code>.
  </p>
  
  <p>
    Lakukan dengan cara membuat folder bernama <code>static</code> di dalam direktori blog:
  </p>
  
  <pre><code>djangogirls ├── blog │ ├── migrasi │ ├── static │   └── template └── mysite
</code></pre>
  
  <p>
    Django secara otomatis akan menemukan folder yang disebut "static" di dalam folder aplikasi Anda. Dan kemudian file ini bisa digunakan isinya sebagai file statis.
  </p>
  
  <h2>
    File CSS pertamamu!
  </h2>
  
  <p>
    Sekarang, mari kita buat file CSS, untuk mempercantik halaman web Anda. Buat sebuah folder bernama <code>css</code> di dalam folder <code>static</code>. Kemudian buat sebuah file bernama <code>blog.css</code> di dalam folder <code>css</code>. Siap?
  </p>
  
  <pre><code>djangogirls
└─── blog
     └─── static
          └─── css
               └─── blog.css
</code></pre>
  
  <p>
    Saatnya menulis CSS! Buka file <code>blog/static/css/blog.css</code> kedalam teks editor mu.
  </p>
  
  <p>
    Kita tidak akan terlalu mendalam mempelajari tentang CSS di sini. Bila ingin belajar lebih mendalam terkait CSS ini Anda bisa kunjungi <a href="https://www.w3schools.com/css/
">halaman ini</a>.
  </p>
  
  <p>
    Tapi kita akan sedikit modifikasi. Mungkin kita akan mengubah warna <i>headers</i> kita. Untuk mengetahui warna, komputer menggunakan kode unik. Kode ini dimulai dengan <code> # &lt;/ 0> diikuti oleh 6 huruf (A-F) dan angka (0-9). Misalnya, kode untuk warna biru adalah &lt;code> #0000FF &lt;/ 0> . Anda dapat menemukan kode warna untuk berbagai warna di sini: http://www.colorpicker.com/. Kamu juga dapat menggunakan &lt;a href="http://www.w3schools.com/colors/colors_names.asp">warna yang telah ditetapkan&lt;/a>, seperti &lt;code>red</code> dan <code>green</code>.
  </p>
  
  <p>
    Dalam berkas <code>blog/static/css/blog.css</code> kamu mesti menambahkan kode seperti berikut:
  </p>
  
  <p>
    {% filename %}blog/static/css/blog.css{% endfilename %}
  </p>
  
  <pre><code class="css">h1 a, h2 a {
    color: #C25100;
}

</code></pre>
  
  <p>
    <code>h1 a</code> adalah selector dalam CSS. Ini berarti kita akan memberikan gaya pada setiap elemen <code>a</code> yang terdapat dalam elemen <code>h1</code>; begitu pula dengan selector <code>h2 a</code>, melakukan hal yang sama. Jadi ketika kita memiliki sesuatu seperti <code>&lt;h1&gt;&lt;a href=""&gt;link&lt;/a&gt;&lt;/h1&gt;</code>, gaya elemen <code>h1 a</code> akanberubah. Dalam kasus ini, kita akan mengubah warnanya menjadi <code>#C25100</code>, ini menandakan warna jingga gelap. Atau kamu bisa memilih sendiri warnanya, tapi pastikan warna tersebut berbeda dengan warna putih dari latar!
  </p>
  
  <p>
    Dalam file CSS kita menentukan gaya untuk elemen yang berada pada file HTML. Mulanya kita menuliskan elemen dengan nama elemen itu sendiri. Kamu mungkin ingat ini merupakan tag dari HTML. Seperti <code>a</code>, <code>h1</code>, dan <code>body</code> adalah contoh dari nama elemen. Kita juga menuliskan elemen dengan atribut <code>class</code> atau atribut <code>id</code>. Nama class dan id ini dimaksudkan untuk elemen-elemen yang kita tuliskan. Class dimaksudkan untuk kumpulan elemen, dan id dimaksudkan untuk elemen tertentu. Misalnya, kamu dapat menuliskan ini dengan menggunakan nama tag <code>a</code>, class <code>external_link</code>, atau id <code>link_to_wiki_page</code>:
  </p>
  
  <pre><code class="html">&lt;a href="https://en.wikipedia.org/wiki/Django" class="external_link" id="link_to_wiki_page"&gt;
</code></pre>
  
  <p>
    Kamu bisa baca lebih lanjut tentang <a href="http://www.w3schools.com/cssref/css_selectors.asp">CSS Selectors di w3schools</a>.
  </p>
  
  <p>
    Kita juga mesti memberti tahu template HTML kita yang telah ditambahkan beberapa CSS. Buka file <code>blog/templates/blog/post_list.html</code> di kode editor dan tambahkan baris ini di paling atas dalam file tersebut:
  </p>
  
  <p>
    {% filename%} blog / templates / blog / post_list.html {% endfilename%}
  </p>
  
  <pre><code class="html">{% load static %}
</code></pre>
  
  <p>
    Kita hanya perlu memuat file statisnya di sini. :) Di antara tag <code>&lt;head&gt;</code> dan <code>&lt;/head&gt;</code>, setelah tautan ke file CSS Bootstrap, tambahkan baris ini:
  </p>
  
  <p>
    {% filename%}blog/templates/blog/post_list.html{% endfilename%}
  </p>
  
  <pre><code class="html">&lt;link rel="stylesheet" href="{% static 'css/blog.css' %}"&gt;
</code></pre>
  
  <p>
    Browser akan membaca file tersebut sesuai urutan, jadi kita perlu memastikan baris tersebut ada di posisi yang tepat. Jika tidak, kode dalam file kita mungkin akan diganti dengan kode dalam file Bootstrap. Kita baru saja menambahakan lokasi file template kita.
  </p>
  
  <p>
    Seharusnya isi dalam filenya seperti ini:
  </p>
  
  <p>
    {% filename%} blog / templates / blog / post_list.html {% endfilename%}
  </p>
  
  <pre><code class="html">{% load static %}
&lt;html&gt;
    &lt;head&gt;
        &lt;title&gt;Django Girls blog&lt;/title&gt;
        &lt;link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css"&gt;
        &lt;link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap-theme.min.css"&gt;
        &lt;link rel="stylesheet" href="{% static 'css/blog.css' %}"&gt;
    &lt;/head&gt;
    &lt;body&gt;
        &lt;div&gt;
            &lt;h1&gt;&lt;a href="/"&gt;Django Girls Blog&lt;/a&gt;&lt;/h1&gt;
        &lt;/div&gt;

        {% for post in posts %}
            &lt;div&gt;
                &lt;p&gt;published: {{ post.published_date }}&lt;/p&gt;
                &lt;h2&gt;&lt;a href=""&gt;{{ post.title }}&lt;/a&gt;&lt;/h2&gt;
                &lt;p&gt;{{ post.text|linebreaksbr }}&lt;/p&gt;
            &lt;/div&gt;
        {% endfor %}
    &lt;/body&gt;
&lt;/html&gt;
</code></pre>
  
  <p>
    OK, simpan file dan segarkan situsnya!
  </p>
  
  <p>
    <img src="images/color2.png" alt="Gambar 14.2" />
  </p>
  
  <p>
    Kerja bagus! Mungkin kita juga akan memberi sedikit ruang pada website kita dan menambahkan margin di sisi luar kiri? Coba ini!
  </p>
  
  <p>
    {% filename%} blog / static / css / blog.css {% endfilename%}
  </p>
  
  <pre><code class="css">body {
     padding-left: 15px;
}
</code></pre>
  
  <p>
    Tambahkan ke CSS kamu, simpan dan lihat hasilnya!
  </p>
  
  <p>
    <img src="images/margin2.png" alt="Gambar 14.3" />
  </p>
  
  <p>
    Mungkin kita bisa mengubah huruf di header kita? Tempelkan ini ke file kamu <code>&lt;head&gt;</code> di <code>blog/templates/blog/post_list.html</code>:
  </p>
  
  <p>
    {% filename%} blog / templates / blog / post_list.html {% endfilename%}
  </p>
  
  <pre><code class="html">&lt;link href="//fonts.googleapis.com/css?family=Lobster&subset=latin,latin-ext" rel="stylesheet" type="text/css"&gt;
</code></pre>
  
  <p>
    Seperti sebelumnya, periksa urutan dan tempat sebelum ditautkan ke <code>blog / static / css / blog.css</code>. Baris ini akan mengimpor huruf yang disebut <em>Lobster</em> dari Google Fonts (https://www.google.com/fonts).
  </p>
  
  <p>
    Temukan blok ini <code>h1 a</code> (kode antara tanda kurung <code>{</code> dan <code>}</code>) di file CSS <code>blog/static/css/blog.css</code>. Sekarang tambahkan baris <code>font-family: 'Lobster';</code> di antara kurung kurawal, dan segarkan halamannya:
  </p>
  
  <p>
    {% filename%}blog/static/css/blog.css{% endfilename%}
  </p>
  
  <pre><code class="css">h1 a, h2 a {
    color: #C25100;
    font-family: 'Lobster';
}
</code></pre>
  
  <p>
    <img src="images/font.png" alt="Gambar 14.3" />
  </p>
  
  <p>
    Bagus!
  </p>
  
  <p>
    Seperti disebutkan di atas, CSS memiliki konsep class. Ini memungkinkan kamu memberi atribut ke dalam bagian kode HTML dan mempercantik hanya pada elemen tertentu, sehingga tidak memengaruhi elemen lain. Ini bisa sangat membantu! Mungkin kamu memiliki dua <code>div</code> dengan fungsi berbeda (seperti header dan postingan kamu). Sebuah class dapat membantu kamu membuatnya telihat berbeda.
  </p>
  
  <p>
    Silakan beri atribut class ke beberapa bagian HTML. Tambahkan sebuah kelas yang disebut <code>page-header</code> ke <code>div</code> yang berisi header kamu, seperti ini:
  </p>
  
  <p>
    {% filename%}blog/templates/blog/post_list.html{% endfilename%}
  </p>
  
  <pre><code class="html">&lt;div class="page-header"&gt;
    &lt;h1&gt;&lt;a href="/"&gt;Django Girls Blog&lt;/a&gt;&lt;/h1&gt;
&lt;/div&gt;

</code></pre>
  
  <p>
    Dan sekarang tambahkan sebuah kelas <code> pos &lt;/ 0> ke &lt;code> div &lt;/ 0> berisi sebuah posting blog.&lt;/p>

&lt;p>{% filename%} blog / templates / blog / post_list.html {% endfilename%}&lt;/p>

&lt;pre>&lt;code class="html">&lt;div class="post"&gt;
    &lt;p&gt;published: {{ post.published_date }}&lt;/p&gt;
    &lt;h2&gt;&lt;a href=""&gt;{{ post.title }}&lt;/a&gt;&lt;/h2&gt;
    &lt;p&gt;{{ post.text|linebreaksbr }}&lt;/p&gt;
&lt;/div&gt;
</code></pre> 
    
    <p>
      Kami sekarang akan menambahkan blok deklarasi ke penyeleksi yang berbeda. Pemilih dimulai dengan <code> . &lt;/ 0> berhubungan dengan kelas. Ada banyak tutorial dan penjelasan bagus tentang CSS di Web yang dapat membantu Anda memahami kode berikut. For now, copy and paste it into your &lt;code>blog/static/css/blog.css</code> file:
    </p>
    
    <p>
      {% filename%} blog / static / css / blog.css {% endfilename%}
    </p>
    
    <pre><code class="css">.page-header {
    background-color: #C25100;
    margin-top: 0;
    padding: 20px 20px 20px 40px;
}

.page-header h1, .page-header h1 a, .page-header h1 a:visited, .page-header h1 a:active {
    color: #ffffff;
    font-size: 36pt;
    text-decoration: none;
}

.content {
    margin-left: 40px;
}

h1, h2, h3, h4 {
    font-family: 'Lobster', cursive;
}

.date {
    color: #828282;
}

.save {
    float: right;
}

.post-form textarea, .post-form input {
    width: 100%;
}

.top-menu, .top-menu:hover, .top-menu:visited {
    color: #ffffff;
    float: right;
    font-size: 26pt;
    margin-right: 20px;
}

.post {
    margin-bottom: 70px;
}

.post h2 a, .post h2 a:visited {
    color: #000000;
}
</code></pre>
    
    <p>
      Kemudian hubungilah kode HTML yang menampilkan tulisan dengan deklarasi kelas. Ganti ini:
    </p>
    
    <p>
      {% filename%} blog / templates / blog / post_list.html {% endfilename%}
    </p>
    
    <pre><code class="html">{% for post in posts %}
    &lt;div class="post"&gt;
        &lt;p&gt;published: {{ post.published_date }}&lt;/p&gt;
        &lt;h2&gt;&lt;a href=""&gt;{{ post.title }}&lt;/a&gt;&lt;/h2&gt;
        &lt;p&gt;{{ post.text|linebreaksbr }}&lt;/p&gt;
    &lt;/div&gt;
{% endfor %}
</code></pre>
    
    <p>
      di <code> blog / templates / blog / post_list.html &lt;/ 0> dengan ini:&lt;/p>

&lt;p>{% filename%} blog / templates / blog / post_list.html {% endfilename%}&lt;/p>

&lt;pre>&lt;code class="html">&lt;div class="content container"&gt;
    &lt;div class="row"&gt;
        &lt;div class="col-md-8"&gt;
            {% for post in posts %}
                &lt;div class="post"&gt;
                    &lt;div class="date"&gt;
                        &lt;p&gt;published: {{ post.published_date }}&lt;/p&gt;
                    &lt;/div&gt;
                    &lt;h2&gt;&lt;a href=""&gt;{{ post.title }}&lt;/a&gt;&lt;/h2&gt;
                    &lt;p&gt;{{ post.text|linebreaksbr }}&lt;/p&gt;
                &lt;/div&gt;
            {% endfor %}
        &lt;/div&gt;
    &lt;/div&gt;
&lt;/div&gt;
</code></pre> 
      
      <p>
        Simpan file tersebut dan segarkan situs Anda.
      </p>
      
      <p>
        <img src="images/final.png" alt="Gambar 14.4" />
      </p>
      
      <p>
        Woo hoo! Terlihat mengagumkan, kan? Lihatlah kode yang baru kita tempel untuk menemukan tempat di mana kita menambahkan kelas dalam HTML dan menggunakannya di CSS. Di mana Anda akan membuat perubahan jika Anda ingin tanggal menjadi turquoise?
      </p>
      
      <p>
        Jangan takut untuk bermain-main dengan CSS ini sedikit dan mencoba untuk mengubah beberapa hal. Bermain dengan CSS dapat membantu Anda memahami hal-hal yang berbeda. Jika Anda memecahkan sesuatu, jangan khawatir - Anda selalu bisa membatalkannya!
      </p>
      
      <p>
        Kami sangat merekomendasikan untuk mengambil online gratis ini <a href="https://www.codecademy.com/tracks/web"> Codeacademy HTML & amp; Kursus CSS </ 0> . Ini dapat membantu Anda mempelajari semua tentang membuat situs web Anda lebih cantik dengan CSS.</p> 
        
        <p>
          Siap untuk bab berikutnya ?! :)
        </p>