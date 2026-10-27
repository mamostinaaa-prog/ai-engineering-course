# ai-engineering-course

## Module 01 — Работа с LLM

Программа отправляет запрос в GigaChat и при ошибке переключается на резервного провайдера HuggingFace.

### Запуск

Установи зависимости:

```bash
pip install -r requirements.txt
```

Создай файл `.env` в корне проекта и добавь свои ключи:

```text
GIGACHAT_CREDENTIALS=your_gigachat_authorization_key
HF_API_KEY=your_huggingface_api_key
```

Запусти программу из корня проекта:

```bash
python3 module_01/llm_client.py
```

### Troubleshooting

**1. GigaChat: `Invalid credentials format`**

Проверь, что `GIGACHAT_CREDENTIALS` содержит корректный Authorization Key в формате Base64. Не используй вместо него Client ID или Client Secret. Удали случайные пробелы и символы в начале и конце значения.

**2. HuggingFace: ошибка `402 — You have no remaining credits`**

Проверь доступные кредиты и условия использования Inference Providers в аккаунте HuggingFace. Если кредиты закончились, используй доступный тариф или другой разрешённый провайдер.

**3. Переключение между провайдерами**

Если GigaChat завершается с ошибкой, программа пытается отправить запрос через HuggingFace. Если оба провайдера недоступны, проверь ключи и доступность сервисов.
