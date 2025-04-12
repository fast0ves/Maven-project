<p align="center">
      <img src="https://i.ibb.co/TxCrLNsm/images.png" width="726">
</p>

## About project and what needed to do

Нужно сделать исполняемый JAR-файл с игрой на JavaFX через графический движок от JavaRush.

ТЗ:

Добавить зависимости:
org.apache.commons: commons-lang3: 3.12.0
org.openjfx: javafx-controls: 18.0.1
com.javarush: desktop-game-engine:1.0 (об этой зависимости будет отдельное задание)
org.junit.jupiter: junit-jupiter-engine: 5.8.2 (с scope test)

Добавить плагины для:
установки зависимости com.javarush: desktop-game-engine:1.0 из библиотеки lib в локальный репозиторий (google в помощь);
плагин maven-compiler-plugin оставить без изменений;
плагин, который соберет все зависимости (с scope compile) и сложит в какую-то директорию при сборке;
плагин maven-jar-plugin, который сделает jar файл, содержащий код игры и зависимости. В этом плагине нужно сконфигурировать файл MANIFEST.MF, чтоб он содержал секции: Class-Path, Main-Class и Rsrc-Main-Class
В Class-Path должны быть прописаны все наши JAR-зависимости.
В Main-Class должен быть прописан класс org.eclipse.jdt.internal.jarinjarloader.JarRsrcLoader, который умеет использовать classpath из JAR-файлов, а также умеет стартовать приложение на JavaFX.
В Rsrc-Main-Class должен быть прописан стартовый класс игры (com.javarush.games.racer.RacerGame).

В плагине maven-surefire-plugin сделать конфигурацию, чтоб тест StrangeTest не запускался при сборке. Остальные тесты должны выполняться.

Добавить секцию “resources”, в которой сказать, что собранные JAR-зависимости это ресурс, чтоб плагин maven-jar-plugin сложил их внутрь JAR-файла в папку lib/


## Developers

- [by fast0ves](https://github.com/fast0ves)
