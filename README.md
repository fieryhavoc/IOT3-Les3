# IOT3-Les3

// JSON libraries
#include <ArduinoJson.h>

// JSON variables
JsonDocument doc;
char jsonOut[128];

void setup() {
    Serial.begin(115200);

    // JSON als tekst
    String jsonData = R"(
    {
      "property": "value",
      "getal": 3.14,
      "boolean": true,
      "string": "string",
      "array": [
        "hallo",
        "allemaal!"
      ],
      "object": {
        "string": "hoi",
        "getal": 42
      }
    }
    )";

    Serial.println("JSON data:");
    Serial.println(jsonData);

    // JSON uit de foto opbouwen
    doc["key1"] = "value";
    doc["key2"] = "value2";

    // JSON document omzetten naar tekst
    serializeJson(doc, jsonOut);

    Serial.println("JSON uit ArduinoJson doc:");
    serializeJson(doc, Serial);
    Serial.println();
}

void loop() {
    Hallo();

    float resultaat = Multiply(3.0, 4.0);

    delay(1000);
}

void Hallo() {
    Serial.println("Hallo!");
}

float Multiply(float a, float b) {
    float c = a * b;
    Serial.println("a * b = " + String(c));
    return c;
}
