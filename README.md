# Ciputra Codding Test

# 1. Check odd or even number
```
const number = [1,2,3,4,5,6,7,8,9,10];
let genap = [];
let ganjil = [];

const checkNumber = async function(dNumber) {
	await dNumber.forEach(data => {
    if(data % 2 == 0) {
      genap.push(data)
    } else {
      ganjil.push(data)
    }
  })
  
  console.log(`${genap.join(',')} = bilangan genap`)
  console.log(`${ganjil.join(',')} = bilangan ganjil`)
}


checkNumber(number)
```

# 2. check kelipatan number
```
const number = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15];

const kelipatan = async function(dNumber) {
	await dNumber.forEach((data, index) => {
  	let tempText = ''
    
    if(Number.isInteger(data / 3)) {
    	tempText += 'TIGA'
    }
    
    if (Number.isInteger(data / 5)) {
    	tempText += 'LIMA'
    } 
    
    if (!Number.isInteger(data / 3) && !Number.isInteger(data / 5)) {
    	tempText += data
    }
    
    console.log(tempText)
  })
}


kelipatan(number)
```

# 3. check revers string
```
<?php
$string = "Anna";

$strRawData = strtolower($string);
$arrRawData = str_split($strRawData);
$strRevData = implode('', array_reverse($arrRawData));

if ($strRawData == $strRevData) {
	print_r("Yes, karena kata '$strRawData' ketika dibalik sama saja yaitu '$strRevData'");
} else {
	print_r("No, karena kata '$strRawData' ketika dibalik tidak sama yaitu '$strRevData'");
}
```

# 4. query database
```
/* TABLE */
CREATE TABLE IF NOT EXISTS `docs` (
  `id` int(6) unsigned NOT NULL,
  `nama` varchar(200) NOT NULL,
  `bulan` varchar(200) NOT NULL,
  `value` bigint(15) NOT NULL,
  PRIMARY KEY (`id`)
) DEFAULT CHARSET=utf8;

/* INSERT */
INSERT INTO `docs` (`id`, `nama`, `bulan`, `value`) VALUES
  ('1', 'ANTON', 'JANUARY', '100000'),
  ('2', 'ANTON', 'JANUARY', '250000'),
  ('3', 'ANTON', 'FEBRUARY', '300000'),
  ('4', 'ANTON', 'FEBRUARY', '100000'),
  ('5', 'DIAN', 'FEBRUARY', '10000');

/* QUERY */
SELECT A.NAMA, IF(SUM(B.VALUE) IS NULL, 0, SUM(B.VALUE)) JANUARY, IF(SUM(C.VALUE) IS NULL, 0, SUM(C.VALUE)) FEBRUARY
FROM ( SELECT NAMA
       FROM docs 
     ) AS A
LEFT JOIN (SELECT NAMA, value, bulan
       FROM docs 
        where bulan = 'JANUARY' 
     ) AS B
ON A.NAMA=B.NAMA
LEFT JOIN ( SELECT NAMA, value, bulan
       FROM docs 
        where bulan = 'FEBRUARY' 
     ) AS C
ON A.NAMA=C.NAMA
GROUP BY A.NAMA
```
