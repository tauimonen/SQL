--Create a table

CREATE TABLE elokuva(
id INT,
nimi VARCHAR(40),
edeltava_id INT,
PRIMARY KEY (id),
UNIQUE (nimi),
FOREIGN KEY (edeltava_id) REFERENCES elokuva);

INSERT INTO elokuva VALUES (1,'Hobitti - Odottamaton matka', NULL);
INSERT INTO elokuva VALUES (2, 'Hobitti - Smaugin autioittama maa', 1);
INSERT INTO elokuva VALUES (3, 'Hobitti - Viiden armeijan taistelu', 2);

INSERT INTO elokuva VALUES (10, 'Tähtien sota', NULL);
INSERT INTO elokuva VALUES (11, 'Imperiumin vastaisku', 10);
INSERT INTO elokuva VALUES (12, 'Jedin paluu', 11);
INSERT INTO elokuva VALUES (13, 'Episodi I - Pimeä uhka', 12);

--Make a query

SELECT id, edeltava_id, 1 AS taso
FROM elokuva

UNION 
SELECT elokuva_1.id, elokuva_2.edeltava_id, 2 AS taso
FROM elokuva elokuva_1
JOIN elokuva elokuva_2 
ON elokuva_1.edeltava_id = elokuva_2.id 
AND elokuva_2.edeltava_id IS NOT NULL

UNION
SELECT elokuva_1.id, elokuva_3.edeltava_id, 3 AS taso
FROM elokuva elokuva_1

JOIN elokuva elokuva_2 
ON elokuva_1.edeltava_id = elokuva_2.id 
AND elokuva_2.edeltava_id IS NOT NULL

JOIN elokuva elokuva_3
ON elokuva_2.edeltava_id = elokuva_3.id 
AND elokuva_3.edeltava_id IS NOT NULL

ORDER BY id, taso;
