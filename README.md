ImageGD
=======

PHP image manipulation with GD



    $img = new ImageGD(array('quality'=>70, 'width'=>'auto', 'height'=>'auto'));
    $img->setString($img_string);
    $img->setFile($img_file);
    $newimg = $img->create(array('width'=>'200', 'height'=>'auto'));
    $newimg->save($dest_file, array('quality'=>80));




    $res = $img->crop(200,0)->saveTo($dest_folder, $options);
    $tn = $img->crop(200,0)->merge($watermark, $options);
    $tn->save($dest_file, $options);
    $tn->out(array('quality'=>80, '')); // output to buffer
