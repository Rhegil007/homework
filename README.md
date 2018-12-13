<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css" integrity="sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO" crossorigin="anonymous">

<?php
$items = [
    ['id' => '1', 'name' => 'Монитор',      'price' => '1200.00', 'stock' => '5', 'disc' => '10'],
    ['id' => '2', 'name' => 'Компьютер',    'price' => '4200.00', 'stock' => '7', 'disc' => '10'],
    ['id' => '3', 'name' => 'Ноутбук',      'price' => '7700.00', 'stock' => '2', 'disc' => '10'],
    ['id' => '4', 'name' => 'Принтер',      'price' => '1800.00', 'stock' => '1', 'disc' => '10'],
    ['id' => '5', 'name' => 'Стол',         'price' => '1100.00', 'stock' => '0', 'disc' => '20'],
    ['id' => '6', 'name' => 'Стул',         'price' => '2200.00', 'stock' => '0', 'disc' => '20'],
    ['id' => '7', 'name' => 'Шкаф',         'price' => '1260.00', 'stock' => '8', 'disc' => '20' ],
    ['id' => '8', 'name' => 'Кресло',       'price' => '4250.00', 'stock' => '9', 'disc' => '20'],
    ['id' => '9', 'name' => 'Диван',        'price' => '9800.00', 'stock' => '1', 'disc' => '30'],
];
$noImage = 'https://upload.wikimedia.org/wikipedia/commons/thumb/a/ac/No_image_available.svg/600px-No_image_available.svg.png';

$images = [
    ['id' => '1', 'img' => 'https://i1.foxtrot.com.ua/product/MediumImages/6283403_0.jpg'],

    ['id' => '2', 'img' => 'https://sistemnik.com.ua/wp-content/uploads/2014/06/comp400.jpg'],
    ['id' => '3', 'img' => 'https://i3.price.ua/images/model/839/2951179/2/1/type4/asus_x541na-go129_3792216.jpg'],
    ['id' => '4', 'img' => 'https://img.mvideo.ru/Pdb/30026269b.jpg'],
    ['id' => '7', 'img' => 'https://lvivmebli.com/upload/catalog/25000/24972/lima_s_1_bialy_dab_sonoma_o.jpg'],
    ['id' => '8', 'img' => 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQgOCkQS4L9jBezaOHMs-g-GJ6_ui4zdCCg3Y6gSyuF_o6gBHMU']
];
   
$description = "Some quick example text to build on the card title and make up the bulk of the card's content.";
?>
<div class="container">
  <div class="row">
    <div class="col-sm">
      <h4 align="center">Column 1.</h4>
      <?php 
    foreach ($items as $item) {
     $id = $item['id'];
     $number = $id % 3;
     if ($number ==0){
     $article = $item['name'];
     $disc = $item ['price'] - ($item ['price'] * $item ['disc'] / 100);
     $price = 'Цена: ' . $disc . ' грн';
     $stock = $item['stock'];
        if($stock < 2){
            $price = 'Цена: ' . (float) $item ['price'] . ' грн';
        }
        if($stock == 0){
            $price = 'Нет в наличии';
        };
    $image = $noImage;
    foreach ($images as $img) {
        if(isset(array_intersect($item,$img)['id'])){
            $image=$img['img'];
            break;
        };
    }
       
 }
}
    ?>
<div class="card text-white bg-dark mb-3" style="max-width: 18rem;">
    <img class="card-img-top" src=<?php echo $image?>>
    <div class="card-body">

        <h5 class="card-title"><?php echo $article?></h5>
        <p class="card-text"><?php echo $description?>.</p>
    </div>
    <div class="card-footer bg-transparent border-primary"><?php echo $price?></div>
</div>



    </div>
    <div class="col-sm">
      <h4 align="center">Column 2.</h4>
      <?php 
    foreach ($items as $item) {
     $id = $item['id'];
     $number = $id % 3;
     if ($number == 1){
     $article = $item['name'];
     $disc = $item ['price'] - ($item ['price'] * $item ['disc'] / 100);
     $price = 'Цена: ' . $disc . ' грн';
     $stock = $item['stock'];
        if($stock < 2){
            $price = 'Цена: ' .(float) $item ['price'] . ' грн';
        }
        if($stock == 0){
            $price = 'Нет в наличии';
        };
    $image = $noImage;
    foreach ($images as $img) {
        if(isset(array_intersect($item,$img)['id'])){
            $image=$img['img'];
            break;
        };
    }
        
 }
}
    ?>
    <div class="card text-white bg-dark mb-3" style="max-width: 18rem;">
    <img class="card-img-top" src=<?php echo $image?>>
    <div class="card-body">

        <h5 class="card-title"><?php echo $number?></h5>
        <p class="card-text"><?php echo $description?>.</p>
    </div>
    <div class="card-footer bg-transparent border-primary"><?php echo $price?></div>
</div>
    </div>
    <div class="col-sm">
      <h4 align="center">Column 3</h4>
      <?php 
    foreach ($items as $item) {
     $id = $item['id'];
     $number = $id % 3;
     if ($number == 2){
     $article = $item['name'];
     $disc = $item ['price'] - ($item ['price'] * $item ['disc'] / 100);
     $price = 'Цена: ' . $disc . ' грн';
     $stock = $item['stock'];
        if($stock < 2){
            $price ='Цена: ' . (float) $item ['price'] . ' грн';
        }
        if($stock == 0){
            $price = 'Нет в наличии';
        };
    $image = $noImage;
    foreach ($images as $img) {
        if(isset(array_intersect($item,$img)['id'])){
            $image=$img['img'];
            break;
        };
    }
        
 }
}
    ?>
    <div class="card text-white bg-dark mb-3" style="max-width: 18rem;">
    <img class="card-img-top" src=<?php echo $image?>>
    <div class="card-body">

        <h5 class="card-title"><?php echo $number?></h5>
        <p class="card-text"><?php echo $description?>.</p>
    </div>
    <div class="card-footer bg-transparent border-primary"><?php echo $price?></div>
</div>
    </div>
  </div>
</div>

<?php 
    echo '
    <table class="table table-bordered">
        <thead>
        <tr>
            <th scope="col">Id</th>
            <th scope="col">Name</th>
            <th scope="col">Price</th>
            <th scope="col">Stock</th>
            <th scope="col">Discount</th>
        </tr>
        </thead>
        <tbody>';
    echo '<br>';
    foreach ($items as $item) {
        echo '<tr><td>' . $item ['id'];
        echo '</td><td>' . $item ['name'];
        echo '</td><td>' . $item ['price'];
        echo '</td><td>' . $item ['stock'];
        echo '</td><td>' . $item ['disc'];
        echo '</td></tr>';
    }
    ?>
