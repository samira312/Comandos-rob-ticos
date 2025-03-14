# Comandos-rob-ticos(H1)
### Seção menor (H3)
if (!isReplaying) { // Permite gravação e controle manual quando não está reproduzindo
    val1 = analogRead(potpin1);
    if (val1 < 100) {
      s1 = s1 - 2;
      if (s1 <= 10) {
        s1 = 10;
      }
      servo1.write(s1);
      delay(25);  // Adiciona um delay para movimento mais lento
    }
    if (val1 > 900) {
      s1 = s1 + 2;
      if (s1 >= 170) {
        s1 = 170;
      }
      servo1.write(s1);
      delay(25);  // Adiciona um delay para movimento mais lento
    }

    // Controle da extensão do braço (s2)
    val2 = analogRead(potpin2);
    if (val2 < 100) {
      s2 = s2 + 2;
      if (s2 >= 140) {
        s2 = 140;
      }

      if (s2 >= 120 && s3 <= 20) {
        s2 = 120;
      }

      servo2.write(s2);
      delay(25);  // Adiciona um delay para movimento mais lento
    }

    if (val2 > 900) {
      s2 = s2 - 2;
      if (s2 <= 10) {
        s2 = 10;
      }

      if (s2 >= 120 && s3 <= 20) {
        s2 = 120;
      }

      servo2.write(s2);
      delay(25);  // Adiciona um delay para movimento mais lento
    }

    // Controle da altura do braço (s3)
    val3 = analogRead(potpin3);
    if (val3 > 900) {
      s3 = s3 - 2;
      if (s3 <= 10) {
        s3 = 10;
      }

      if (s2 >= 120 && s2 < 130 && s3 <= 20) {
        s3 = 20;
      }
      else if (s2 >= 130 && s2 < 140 && s3 <= 30) {
        s3 = 30;
      }
      else if (s2 == 140 && s3 <= 65) {
        s3 = 65;
      }

      servo3.write(s3);
      delay(25);  // Adiciona um delay para movimento mais lento
    }

    if (val3 < 100) {
      s3 = s3 + 2;
      if (s3 >= 170) {
        s3 = 170;
      }

      if (s2 >= 120 && s2 < 130 && s3 <= 20) {
        s3 = 20;
      }
      else if (s2 >= 130 && s2 < 140 && s3 <= 30) {
        s3 = 30;
      }
      else if (s2 == 140 && s3 <= 65) {
        s3 = 65;
      }

      servo3.write(s3);
      delay(25);  // Adiciona um delay para movimento mais lento
    }

    // Controle da garra do braço    val4 = analogRead(potpin4);
    if (val4 < 100) {
      s4 = s4 + 2;
      if (s4 < 0) {
        s4 = 0;
      }
      servo4.write(s4);
      delay(25);  // Adiciona um delay para movimento mais lento
    }
    if (val4 > 900) {
      s4 = s4 - 2;
      
      if (s4 > 30) {
        s4 = 30;
      }

      if(s4 < 0)
      {
        s4 = 0;
      }

      servo4.write(s4);
      delay(25);  // Adiciona um delay para movimento mais lento
    }
