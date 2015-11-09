# athento-nx-eni
Esquema Nacional de Interoperabilidad

# Summary
Este add-on incluye la compatibilidad con el Esquema Nacional de Interoperabilidad sobre aquellos tipos documentales donde se declare la faceta DocumentoEni.

Ésto incluye:

* Esquema de metadatos (según Guía de Adecuación al ENI de http://www.administracionelectronica.gob.es
* Esquema de firmas de http://www.administracionelectronica.gob.es
* Esquema de contenido de http://www.administracionelectronica.gob.es
* Nueva pestaña disponible para visualizar los metadatos
* Capacidad para que un usuario administrador pueda editar esos metadatos mediante interfaz
* Capacidad vía API para operar con estos metadatos, permitiendo la integración de terceros

# Default configuration

Por defecto, este plugin añade capacidad ENI a los siguientes tipos documentales de Nuxeo:

* File
* Picture

Para modificar esta configuración, o añadir nuevos metadatos, habría que crear una contribución a un punto de extensión como el siguiente:

<?xml version="1.0" encoding="UTF-8"?>

<component name="org.athento.nuxeo.eni.documentoeni.doctype" version="1.0.0">
		
	<require>org.nuxeo.runtime.started</require>

	<extension target="org.nuxeo.ecm.core.schema.TypeService" point="doctype">
		
		<doctype name="My_Custom_ENI_Compliant_Doctype" append="true">
			<facet name="documentoEniFacet"/>
		</doctype>
		
	</extension>

</component>
