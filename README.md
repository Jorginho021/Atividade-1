# Atividade-1


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="16dp"
    android:gravity="center"
    android:background="#E0F7FA"> <!-- Cor de fundo alterada -->

    <!-- Texto de boas-vindas com seu nome -->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Bem-vindo ao app do Seu Nome!"
        android:textSize="22sp"
        android:textStyle="bold"
        android:layout_marginBottom="24dp" />

    <!-- Campo de texto (EditText) -->
    <EditText
        android:id="@+id/etEntrada"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Digite algo aqui..."
        android:layout_marginBottom="16dp" />

    <!-- Primeiro Botão -->
    <Button
        android:id="@+id/btnPrimeiro"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Botão 1"
        android:layout_marginBottom="8dp" />

    <!-- Segundo Botão com mensagem diferente -->
    <Button
        android:id="@+id/btnSegundo"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Exibir Mensagem" />

</LinearLayout>





package com.exemplo.meuapp

import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.Toast
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // Referências aos elementos da tela
        val etEntrada = findViewById<EditText>(R.id.etEntrada)
        val btnPrimeiro = findViewById<Button>(R.id.btnPrimeiro)
        val btnSegundo = findViewById<Button>(R.id.btnSegundo)

        // Ação do Primeiro Botão
        btnPrimeiro.setOnClickListener {
            Toast.makeText(this, "Você clicou no primeiro botão!", Toast.LENGTH_SHORT).show()
        }

        // Ação do Segundo Botão (Desafio: exibe no Toast o que foi digitado)
        btnSegundo.setOnClickListener {
            val textoDigitado = etEntrada.text.toString()

            if (textoDigitado.isNotEmpty()) {
                Toast.makeText(this, textoDigitado, Toast.LENGTH_SHORT).show()
            } else {
                Toast.makeText(this, "Por favor, digite algo!", Toast.LENGTH_SHORT).show()
            }
        }
    }
}
