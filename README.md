# ImageByText

Разместить файл imgtext.php и файл шрифта в одной директории на сервере.
После этого в нужном месте страницы разместить изображение вида:

```
<img src="/ImageByText/imgtext.php?text=Нужный текст&fsize=24&align=left&deg=90">
```

Если нужен перевод строки, то либо вручную вводить символ %0A, либо генерировать ссылку на php:
```
<?php
    $link = "/ImageByText/imgtext.php?" . http_build_query(["text" => "Нужный\nтекст", "fsize" => "24", "align" => "left", "deg" => 90]);
?>
<img src="<?php echo $link;?>">
```

Или вставлять через js (нужен jQuery)
```
<script>
    link = "/ImageByText/imgtext.php?" + $.param({"text": 'Нужный\nтекст', "fsize": "24", "align": "left", "deg": 90});
    $(document).find('body').append($("<img/>", {src: link}));
</script>
```
