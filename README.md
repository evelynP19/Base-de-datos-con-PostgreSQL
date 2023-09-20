# Base-de-datos-con-PostgreSQL
Utilizaremos una base de datos correspondiente al alquiler de peliculas, revisaremos a detalle como se crean las funciones, triggers, CTE y diversas aplicaciones que nos ofrece el manejador de datos PostgreSQL. 
#Creando una funcion como un procedimiento 
CREATE OR REPLACE FUNCTION test_dropcreate_function()
RETURNS VOID
LANGUAGE plpgsql
AS $$
BEGIN
	DROP TABLE IF EXISTS aaa;
	CREATE TABLE aaa (bbb char(5) CONSTRAINT firstkey PRIMARY KEY, ccc char(5));
	DROP TABLE IF EXISTS aaab;
	CREATE TABLE aaab (bbba char(5) CONSTRAINT secondkey SECOND KEY, ccca char(5));
END
$$;

SELECT test_dropcreate_function();
