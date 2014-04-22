Image Handling with GD
=======

PHP image manipulation with GD



### Structure

    // GD Wrapper
    $img = new Image($gd);
    $img = $img->merge($img2);
    $img = $img->merge($img3);
    $img = $img->merge($img4);
    $img = $img->merge($img5);
    $img = $img->merge($img6);
    $img->save($to_file, array('quality'=>70, 'type'=>'jpg'));


    // Image Layers
    // Set background canvas
    $m = new ImageLayers(array('w'=>800,'h'=>600,'bg'=>'ffffff'));
    
    // First image used as canvas
    $m = new ImageLayers();
    $m = $m->addFile($img2);
    $m = $m->addFile($img3);
    $m = $m->addFile($img4);
    $m = $m->addFile($img5);
    $m = $m->addFile($img6);
    // Merge the layers
    $m = $m->merge();
    // Create an Image GD Object and return it
    $img = $m->createGD();
    // Create an Image Object and return it
    $img = $m->createImage();
    // Save the image
    $img->save($to_file, array('quality'=>70, 'type'=>'jpg'));
    
    

### Usage
    
    // Set default options for image creation
    $layers = new ImageLayers(array('width'=>'auto','height'=>'auto', 'default_type'=>'jpeg', 'align'=>'center'));
    $layers = $layers->addFile($img, $options);
    $layers = $layers->addFile($watermark, $options);
    $img = $layers->createImage();
    $img->save($file, $options);
    
### Resample existing image

    $img = new Image($gd, $default_options);
    // options can be an array
    $img->resample($options);
    // options can be a callback
    $img->resample(function($img, $default_options){
        $opts = $default_options;
        if($img->width > 200){
            $opts['width'] = 200;
        }
        return $opts;
    });
