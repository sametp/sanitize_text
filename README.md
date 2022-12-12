# sanitize_text


$fileName = "";

function sanitaze_text( $value ) {
    $specialFrom = array("/Ğ/","/Ü/","/Ş/","/İ/","/Ö/","/Ç/","/ğ/","/ü/","/ş/","/ı/","/ö/","/ç/");
    $spacialTo = array("G","U","S","I","O","C","g","u","s","i","o","c");
    $value = preg_replace("/[^0-9a-zA-ZÄzÜŞİÖÇğüşıöç]/"," ",$value);
    $value = preg_replace($specialFrom,$spacialTo,$value);
    $value = preg_replace("/ +/"," ",$value);
    $value = preg_replace("/ /","-",$value);
    $value = preg_replace("/\s/","",$value);
    $value = strtolower($value);
    $value = preg_replace("/^-/","",$value);
    $value = preg_replace("/-$/","",$value);
    return $value;
}


echo sanitaze_text($fileName);
