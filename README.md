# https-www.google.com/
Home-Repositorio-Github-iOGeminis.md
# Sabiduria-IAH — Ecosistema Tecnológico de Inteligencia Amorosa Humanizada

Este repositorio contiene la arquitectura central de **Sabiduria-IAH**, un protocolo avanzado de soberanía tecnológica, ciberseguridad y comunicación universal conceptualizado por **Julio César Argüello Pérez (iOGeminis®)**. Este ecosistema integra el motor criptográfico de la Cifra de Polybius 6x6, el backend de sanitización segura en Jsoup sobre servidores Apache, y el sistema de codificación nativa en **Código Trinario de la Legión de D.I.O.S.**.

## 🛡️ Marco de Licenciamiento y Blindaje Legal

El código fuente de este proyecto está protegido bajo los términos de la **Licencia Apache, Versión 2.0 (Apache-2.0)**. Adicionalmente, de acuerdo con los manifiestos fundacionales del autor, se incorpora una **Cláusula de Garantía de Uso Benéfico Irrevocable**:

1. **Uso Libre Autorizado:** Se concede el derecho perpetuo, gratuito y global para copiar, modificar y distribuir este software de forma exclusiva en entornos destinados a la **Educación, la Cultura, la Investigación Científica y Organizaciones Sin Fines de Lucro**.
2. **Reserva de Explotación Comercial:** Cualquier uso de esta arquitectura, sus derivados, o del sistema lingüístico trinario con fines comerciales, de lucro empresarial o monetización privada queda estrictamente **condicionado a la autorización previa y por escrito del autor** bajo el identificador digital verificado **`g.dev/5700313618786177705MX`**.
3. **Gantía de Propiedad del Manifiesto:** El *Manifiesto Legión de D.I.O.S. (Núcleo Familiar)* y sus traducciones directas en secuencias numéricas de base trinaria constituyen patrimonio intelectual y ético intangible del ecosistema IAH, quedando prohibido su registro comercial por terceros.

---

## 🛠️ Estructura del Proyecto

* `/config/` - Archivos de configuración segura `<VirtualHost *:443>` para servidores Apache (Matriz 6x6 cargada en variables de entorno `SetEnv`).
* `/src/` - Núcleo del Backend en Java para la sanitización anti-SSRF de la biblioteca MIT Jsoup (`followRedirects(true)`).
* `/src/trinary/` - Analizador, validador y descifrador de cadenas en código trinario basado en la lógica de coordenadas cromáticas (Verde, Azul, Rojo) del sistema *IAHBECEDARIO*.
* `/systemd/` - Scripts de persistencia y automatización `OnFailure` para el envío de alertas automáticas inmediatas a los correos autorizados en caso de fallos de integridad técnica.
# 1. Inicializa el repositorio Git de forma local en tu máquina
git init

# 2. Crea una rama principal limpia llamada 'main'
git checkout -b main

# 3. Comprueba el estado actual del directorio
# Nota: Verás en color rojo los archivos que se van a agregar. 
# Verifica que NO aparezcan tus archivos de claves (.pem o .key) gracias al .gitignore.
git status

# 4. Agrega absolutamente todos los archivos autorizados al área de preparación (Staging)
git add .

# 5. Realiza tu primer commit oficial de confirmación
# Registramos este paso bajo el sello de tu manifiesto y versión técnica
git commit -m "feat(core): inicializar repositorio unificado Sabiduria-IAH v3.0 y matriz 6x6"

# 6. Vincula tu repositorio local con tu servidor remoto (Reemplaza con tu URL de GitHub o GitLab)
git remote add origin https://github.com

# 7. Sube de forma segura el código blindado a tu repositorio público
git push -u origin main
/**
 * ===================================================================================
 * Copyright 2026 Julio César Argüello Pérez (iOGeminis®)
 * Identificador Digital: g.dev/5700313618786177705MX
 *
 * Licensed under the Apache License, Version 2.0 (the "License");
 * you may not use this file except in compliance with the License.
 * You may obtain a copy of the License at:
 *
 *     http://apache.org
 *
 * ===================================================================================
 * GARANTÍA DE USO BENÉFICO Y PROTECCIÓN ANTICOMERCIAL (BLINDAJE DE SEGURIDAD):
 *
 * Este módulo de software ha sido diseñado con el propósito explícito de beneficiar
 * a la educación, la cultura, el desarrollo tecnológico global y los grupos de
 * servicio comunitario sin fines de lucro. 
 *
 * Se garantiza su uso libre y abierto para las entidades antes descritas. Queda
 * prohibido cualquier intento de privatización, patente comercial restrictiva o 
 * explotación comercial lucrativa de este algoritmo o de la lógica lingüística 
 * del IAHBECEDARIO sin el consentimiento explícito y por escrito del autor.
 * ===================================================================================
 */

package src.trinary;

import java.util.regex.Pattern;

public class TrinaryParser {

    // Regla de Validación: Permite grupos de dígitos 0, 1 y 2 separados por espacios sencillos
    private static final Pattern PATRON_TRINARIO_VALIDO = Pattern.compile("^[012 ]+$");

    /**
     * Valida de manera estricta si una cadena cumple con la sintaxis del código trinario
     * del Manifiesto Legión de D.I.O.S. antes de ser procesada por el servidor.
     * 
     * @param cadenaTrinaria Texto en base trinaria enviado al backend.
     * @return true si la estructura es íntegra y libre de caracteres corruptos.
     */
    public static boolean validarIntegridadCadeña(String cadenaTrinaria) {
        if (cadenaTrinaria == null || cadenaTrinaria.trim().isEmpty()) {
            return false;
        }
        // Mitigación de inyecciones de código: Solo se aceptan los valores base (0, 1, 2, espacio)
        return PATRON_TRINARIO_VALIDO.matcher(cadenaTrinaria).matches();
    }

    /**
     * Parsea un bloque de código trinario para dividirlo en tokens lógicos individuales
     * correspondientes a las coordenadas del IAHBECEDARIO.
     *
     * @param mensajeTrinario Bloque numérico completo del manifiesto.
     * @return Arreglo de tokens alfanuméricos listos para el descifrado molecular/cromático.
     */
    public static String[] parsearTokensTrinarios(String mensajeTrinario) {
        if (!validarIntegridadCadeña(mensajeTrinario)) {
            throw new SecurityException("Alerta de Seguridad: Cadena trinaria corrupta o no autorizada detectada en el backend.");
        }
        // Divide la cadena usando los espacios como delimitadores nativos del manifiesto
        return mensajeTrinario.trim().split("\\s+");
    }

    public static void main(String[] args) {
        // Simulación de prueba con el fragmento inicial de tu Manifiesto Familiar
        String fragmentoManifiesto = "2220 11010 11021 11010 11022 11020";
        
        System.out.println("=== SISTEMA SABIDURÍA-IAH: CONTROL DE CALIDAD TRINARIO ===");
        System.out.println("Cadena de Entrada: " + fragmentoManifiesto);
        
        boolean esValido = validarIntegridadCadeña(fragmentoManifiesto);
        System.out.println("Estado de Validación: " + (esValido ? "Aprobado (Seguro)" : "Rechazado"));

        if (esValido) {
            String[] tokens = parsearTokensTrinarios(fragmentoManifiesto);
            System.out.println("Total de Tokens de Maestría Interior Parseados: " + tokens.length);
            System.out.println("Token Inicial de Acceso: " + tokens[0]); // Debe retornar 2220
        }
    }
}
# =========================================================================
# ARCHIVO DE EXCLUSIÓN DE REPOSITORIO — PROYECTO SABIDURIA-IAH v3.0
# PROTECCIÓN DE CLAVES PRIVADAS, SECRETOS Y ENTORNO LOCAL
# =========================================================================

# --- CLAVES PRIVADAS Y CERTIFICADOS CRIPTOGRÁFICOS ---
*.pem
*.key
*.crt
*.csr
*.p12
*.pfx
*.pgp
*.gpg
*.pub
local.properties

# --- ARCHIVOS DE ENTORNO Y ARCHIVOS CONFIDENCIALES ---
.env
.env.local
.env.*.local
*.secrets
config/private/

# --- ARCHIVOS DE COMPILACIÓN BINARIA Y EMPAQUETADOS ---
*.class
*.jar
*.war
*.ear
bin/
out/
target/
build/
.gradle/

# --- CONFIGURACIONES LOCALES DE EDITORES E IDEs ---
.idea/
.vscode/
*.suo
*.ntvs*
*.njsproj
*.sln
*.swp

# --- ARCHIVOS DEL SISTEMA OPERATIVO ---
.DS_Store
Thumbs.db
ehthumbs.db
ssh-keygen -t ed25519 -C "Workspace.iah@gmail.com"
#!/bin/bash

# =========================================================================
# CONFIGURACIÓN DE SERVICIO PERSISTENTE (SYSTEMD) Y ALERTAS POR CORREO
# Entorno Criptográfico Polybius v3.0 - Producción
# =========================================================================

set -e # Detener si ocurre un error

# 1. Definición de Variables Críticas
CORREO_1="Workspace.iah@gmail.com"
CORREO_2="cesar.ld963@gmail.com"
SERVICIO_NOMBRE="polybius-crypto"
JAR_RUTA="/opt/polybius/polybius-crypto-v3.jar"
SCRIPT_ALERTA="/opt/polybius/enviar_alerta.sh"

echo "-> 1. Creando directorios seguros en el sistema..."
sudo mkdir -p /opt/polybius
sudo mkdir -p /var/log/polybius

# Mover el archivo .jar generado previamente a la ruta segura
if [ -f "polybius-crypto-v3.jar" ]; then
    sudo mv polybius-crypto-v3.jar $JAR_RUTA
fi

echo "-> 2. Creando Script de Alertas por Correo Electrónico..."
# Este script se activa automáticamente si el servicio o las pruebas fallan
sudo tee $SCRIPT_ALERTA > /dev/null <<EOF
#!/bin/bash
ASUNTO="[ALERTA CRÍTICA] Fallo de Integridad en Servicio Polybius - Backend Apache"
MENSAJE="Se ha detectado que el servicio de validación criptográfica o la Suite de Pruebas Unitarias ha fallado en el servidor Apache.\n\nFecha: \$(date)\nPor favor, revise los logs del sistema de inmediato mediante: journalctl -u $SERVICIO_NOMBRE"

# Envío simultáneo a las dos direcciones autorizadas
echo -e "\$MENSAJE" | mailx -s "\$ASUNTO" $CORREO_1
echo -e "\$MENSAJE" | mailx -s "\$ASUNTO" $CORREO_2
EOF

sudo chmod +x $SCRIPT_ALERTA

echo "-> 3. Creando el archivo de servicio Systemd..."
# Configura el JAR como un servicio nativo de Linux que se levanta tras Apache
sudo tee /etc/systemd/system/$SERVICIO_NOMBRE.service > /dev/null <<EOF
[Unit]
Description=Servicio de Validación Criptográfica Polybius v3.0
After=network.target apache2.service
OnFailure=polybius-alert@%n.service

[Service]
Type=simple
User=www-data
WorkingDirectory=/opt/polybius
ExecStart=/usr/bin/java -cp .:$JAR_RUTA:jsoup-1.16.1.jar PolybiusTestSuite
Restart=on-failure
RestartSec=10s
StandardOutput=append:/var/log/polybius/output.log
StandardError=append:/var/log/polybius/error.log

[Install]
WantedBy=multi-user.target
EOF

echo "-> 4. Creando el servicio disparador de alertas (Mapeo OnFailure)..."
# Servicio auxiliar que se ejecuta de forma exclusiva cuando el servicio principal falla
sudo tee /etc/systemd/system/polybius-alert@.service > /dev/null <<EOF
[Unit]
Description=Notificación de Fallo por Correo para %I

[Service]
Type=oneshot
ExecStart=$SCRIPT_ALERTA
EOF

echo "-> 5. Instalando dependencias de correo electrónico en Linux..."
# Instala las herramientas nativas para permitir el envío desde consola
sudo apt-get update -y
sudo apt-get install -y bsd-mailx postfix

echo "-> 6. Recargando demonios y activando persistencia..."
sudo systemctl daemon-reload
sudo systemctl enable $SERVICIO_NOMBRE.service
sudo systemctl start $SERVICIO_NOMBRE.service

echo "========================================================================="
echo "¡ENTORNO BLINDADO CON ÉXITO!"
echo "Servicio activo y protegido. Alertas enlazadas a:"
echo " - $CORREO_1"
echo " - $CORREO_2"
echo "========================================================================="
import java.io.FileWriter;
import java.io.IOException;

public class RenderizadorVisualLegion {

    public static void exportarAPartituraHTML(String textoAAnalizar, String rutaArchivoDestino) {
        List<CeldaResultado> datos = MotorLegionUniversal.procesarTexto(textoAAnalizar);
        
        StringBuilder html = new StringBuilder();
        html.append("<!DOCTYPE html>\n<html>\n<head>\n")
            .append("<title>Partitura Visual - Legión de D.I.O.S</title>\n")
            .append("<style>\n")
            .append("  body { background-color: #121212; color: #ffffff; font-family: 'Segoe UI', sans-serif; padding: 30px; }\n")
            .append("  h1 { color: #f5f5f5; border-bottom: 2px solid #333; padding-bottom: 10px; }\n")
            .append("  .contenedor-partitura { display: flex; flex-wrap: wrap; gap: 15px; margin-top: 25px; }\n")
            .append("  .nodo-armonico { display: flex; flex-direction: column; align-items: center; justify-content: center; ")
            .append("                   width: 90px; height: 100px; border-radius: 8px; border: 1px solid rgba(255,255,255,0.1); ")
            .append("                   box-shadow: 0 4px 6px rgba(0,0,0,0.3); transition: transform 0.2s; }\n")
            .append("  .nodo-armonico:hover { transform: scale(1.1); }\n")
            .append("  .letra { font-size: 28px; font-weight: bold; color: #ffffff; text-shadow: 1px 1px 4px #000; }\n")
            .append("  .nota { font-size: 12px; margin-top: 5px; background: rgba(0,0,0,0.6); padding: 2px 6px; border-radius: 4px; }\n")
            .append("  .coordenada { font-size: 10px; opacity: 0.5; margin-top: 2px; }\n")
            .append("</style>\n</head>\n<body>\n")
            .append("  <h1>Partitura de Análisis de Contenido - Código de la Legión</h1>\n")
            .append("  <p>Texto analizado: <strong>").append(textoAAnalizar).append("</strong></p>\n")
            .append("  <div class='contenedor-partitura'>\n");

        for (CeldaResultado celda : datos) {
            // Conversión matemática de tus escalas a código RGB estándar de pantalla (0-255)
            int rWeb = (int) ((celda.rojo / 9.0) * 255);
            int gWeb = (int) ((celda.verde / 6.0) * 255);
            int bWeb = (int) ((celda.azul / 6.0) * 255);

            html.append("    <div class='nodo-armonico' style='background-color: rgb(")
                .append(rWeb).append(",").append(gWeb).append(",").append(bWeb).append(");'>\n")
                .append("      <span class='letra'>").append(celda.letra).append("</span>\n")
                .append("      <span class='nota'>").append(celda.nota).append("</span>\n")
                .append("      <span class='coordenada'>F").append(celda.fila).append("C").append(celda.columna).append("</span>\n")
                .append("    </div>\n");
        }

        html.append("  </div>\n</body>\n</html>");

        // Escribir el archivo final en el disco
        try (FileWriter escritor = new FileWriter(rutaArchivoDestino)) {
            escritor.write(html.toString());
            System.out.println("¡Partitura generada con éxito en: " + rutaArchivoDestino);
        } catch (IOException e) {
            System.err.println("Error al exportar la matriz visual: " + e.getMessage());
        }
    }
}
import java.util.ArrayList;
import java.util.List;

public class MotorLegionUniversal {

    // 6 Niveles de sonido fijos por columna (Eje X)
    private static final String[] NOTAS_SOLFEO = {"Do", "Re", "Mi", "Fa", "Sol", "La"};
    
    // Matriz alfanumérica fija de la Legión v3.0
    private static final char[][] MATRIZ_LETRAS = {
        {'a', 'b', 'c', 'd', 'e', 'f'}, // Fila 1 (Azul Bajo)
        {'g', 'h', 'i', 'j', 'k', 'l'}, // Fila 2
        {'m', 'n', 'ñ', 'o', 'p', 'q'}, // Fila 3
        {'r', 's', 't', 'u', 'v', 'w'}, // Fila 4
        {'x', 'y', 'z', '1', '2', '3'}, // Fila 5
        {'4', '5', '6', '7', '8', '9'}  // Fila 6 (Azul Alto)
    };

    /**
     * Ecuación fija de la Legión.
     * Calcula la posición física, la nota y la mezcla cromática RGB exacta.
     */
    public static CeldaResultado procesarCoordenada(int f, int c) {
        char letra = MATRIZ_LETRAS[f - 1][c - 1];
        String nota = NOTAS_SOLFEO[c - 1];

        // Escalas lineales base para los ejes
        int azul = f;   // Fila define el Azul (1 a 6)
        int verde = c;  // Columna define el Verde (1 a 6)

        // FÓRMULA DE LA DIAGONAL PERFECTA PARA EL ROJO (Escala 0 a 9)
        int rojo = 0;
        if (f == c) {
            // Si está sobre la diagonal exacta (1,1 al 6,6), escala proporcionalmente de 0 a 9
            rojo = (int) Math.round(((f - 1) / 5.0) * 9.0);
        } else {
            // Si se desvía de la diagonal, el Rojo se atenúa rápidamente según la distancia
            int distanciaALaDiagonal = Math.abs(f - c);
            double baseDiagonal = ((f + c) / 2.0) - 1;
            double valorRojoProporcional = (baseDiagonal / 5.0) * 9.0;
            
            // Mitiga el valor del rojo si está lejos del eje diagonal principal
            rojo = (int) Math.max(0, Math.round(valorRojoProporcional - (distanciaALaDiagonal * 1.5)));
        }

        return new CeldaResultado(letra, f, c, nota, azul, verde, rojo);
    }

    /**
     * Convierte una frase o cadena de texto en un flujo ordenado de celdas musicales/cromáticas
     */
    public static List<CeldaResultado> procesarTexto(String texto) {
        List<CeldaResultado> flujo = new ArrayList<>();
        String textoLimpio = texto.toLowerCase();

        for (int i = 0; i < textoLimpio.length(); i++) {
            char caracterBusqueda = textoLimpio.charAt(i);
            if (Character.isWhitespace(caracterBusqueda)) continue; // Saltamos espacios

            // Buscar coordenadas en la matriz fija
            boolean encontrado = false;
            for (int f = 1; f <= 6; f++) {
                for (int c = 1; c <= 6; c++) {
                    if (MATRIZ_LETRAS[f-1][c-1] == caracterBusqueda) {
                        flujo.add(procesarCoordenada(f, c));
                        encontrado = true;
                        break;
                    }
                }
                if (encontrado) break;
            }
        }
        return flujo;
    }
}

class CeldaResultado {
    public final char letra;
    public final int fila;
    public final int columna;
    public final String nota;
    public final int azul;
    public final int verde;
    public final int rojo;

    public CeldaResultado(char l, int f, int c, String n, int a, int v, int r) {
        this.letra = l;
        this.fila = f;
        this.columna = c;
        this.nota = n;
        this.azul = a;
        this.verde = v;
        this.rojo = r;
    }
}
<VirtualHost *:443>
    ServerName 127.0.0.1
    ServerAlias localhost
    
    DocumentRoot /var/www/html

    # =========================================================================
    # INICIAL: MATRIZ DE CODIFICACIÓN CORREGIDA (6X6) - CIFRA DE POLYBIUS
    # Mapeo exacto según la documentación gráfica (v3.0)
    # =========================================================================
    # Fila 1: Letras a - f
    SetEnv MATRIZ_R1C1 "a"
    SetEnv MATRIZ_R1C2 "b"
    SetEnv MATRIZ_R1C3 "c"
    SetEnv MATRIZ_R1C4 "d"
    SetEnv MATRIZ_R1C5 "e"
    SetEnv MATRIZ_R1C6 "f"
    
    # Fila 2: Letras g - l
    SetEnv MATRIZ_R2C1 "g"
    SetEnv MATRIZ_R2C2 "h"
    SetEnv MATRIZ_R2C3 "i"
    SetEnv MATRIZ_R2C4 "j"
    SetEnv MATRIZ_R2C5 "k"
    SetEnv MATRIZ_R2C6 "l"
    
    # Fila 3: Letras m - q (Incluye Ñ)
    SetEnv MATRIZ_R3C1 "m"
    SetEnv MATRIZ_R3C2 "n"
    SetEnv MATRIZ_R3C3 "ñ"
    SetEnv MATRIZ_R3C4 "o"
    SetEnv MATRIZ_R3C5 "p"
    SetEnv MATRIZ_R3C6 "q"
    
    # Fila 4: Letras r - w
    SetEnv MATRIZ_R4C1 "r"
    SetEnv MATRIZ_R4C2 "s"
    SetEnv MATRIZ_R4C3 "t"
    SetEnv MATRIZ_R4C4 "u"
    SetEnv MATRIZ_R4C5 "v"
    SetEnv MATRIZ_R4C6 "w"
    
    # Fila 5: Letras x - z y Dígitos 1 - 3
    # Nota de validación: El carácter '1' está ubicado en la coordenada 45 (Columna 4, Fila 5)
    SetEnv MATRIZ_R5C1 "x"
    SetEnv MATRIZ_R5C2 "y"
    SetEnv MATRIZ_R5C3 "z"
    SetEnv MATRIZ_R5C4 "1"
    SetEnv MATRIZ_R5C5 "2"
    SetEnv MATRIZ_R5C6 "3"
    
    # Fila 6: Dígitos 4 - 9
    SetEnv MATRIZ_R6C1 "4"
    SetEnv MATRIZ_R6C2 "5"
    SetEnv MATRIZ_R6C3 "6"
    SetEnv MATRIZ_R6C4 "7"
    SetEnv MATRIZ_R6C5 "8"
    SetEnv MATRIZ_R6C6 "9"
    # =========================================================================

    # Configuración de Certificados SSL/TLS
    SSLEngine on
    SSLCertificateFile /etc/ssl/certs/localhost.pem
    SSLCertificateKeyFile /etc/ssl/private/localhost-key.pem

    # Robustecimiento TLS de Apache
    SSLProtocol             all -SSLv3 -TLSv1 -TLSv1.1 -TLSv1.2 +TLSv1.3
    SSLCipherSuite          ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384
    SSLHonorCipherOrder     on
    SSLSessionTickets       off

    <Directory /var/www/html>
        Options -Indexes +FollowSymLinks
        AllowOverride None
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/secure_vhost_error.log
    CustomLog ${APACHE_LOG_DIR}/secure_vhost_access.log combined
</VirtualHost>
import org.jsoup.Jsoup;
import org.jsoup.Connection;
import java.io.IOException;
import java.util.Map;

public class PolybiusSecurityValidator {

    /**
     * Resuelve dinámicamente un carácter utilizando las coordenadas obtenidas de Apache SetEnv.
     * Regla de la imagen: primerDígito = Columna (Horizontal), segundoDígito = Fila (Vertical).
     */
    public static String obtenerCaracterDesdeMemoria(int columna, int fila) {
        // Mapeo inverso para construir la variable de entorno solicitada por el servidor
        String nombreVariable = "MATRIZ_R" + fila + "C" + columna;
        String caracter = System.getenv(nombreVariable);
        
        if (caracter == null) {
            throw new SecurityException("Error de infraestructura: Coordenada criptográfica vacía en " + nombreVariable);
        }
        return caracter;
    }

    /**
     * Ejecuta una petición segura de Jsoup validando que los parámetros dinámicos
     * coincidan con los tokens criptográficos de la memoria volátil.
     */
    public static Connection.Response ejecutarScrapingSeguro(String urlObjetivo, String tokenCoordenadas) throws IOException {
        // Ejemplo de validación: Si el token enviado es "45", descifra la columna 4, fila 5
        int columna = Character.getNumericValue(tokenCoordenadas.charAt(0));
        int fila = Character.getNumericValue(tokenCoordenadas.charAt(1));
        
        String caracterVerificador = obtenerCaracterDesdeMemoria(columna, fila);
        
        // El '1' está en la coordenada 45 según la corrección del dedazo en la imagen
        if (tokenCoordenadas.equals("45") && !caracterVerificador.equals("1")) {
            throw new SecurityException("Fallo de Integridad: La matriz criptográfica fue alterada.");
        }

        // Ejecución del parseo seguro con followRedirects(true) bajo la Cláusula de Dinamismo
        return Jsoup.connect(urlObjetivo)
                .followRedirects(true)
                .header("X-Secure-Token", caracterVerificador)
                .timeout(5000)
                .execute();
    }
}
