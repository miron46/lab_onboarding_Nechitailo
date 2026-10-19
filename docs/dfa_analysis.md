# DFA: Def-Use анализ

## Переменная: log_entry
- Def: строка 2 (log_entry = "Start processing")
- Def: строка 11 (log_entry = "Transaction finished with status: " + status)
- Use: строка 13 (file.write(log_entry))

## Переменная: status
- Def: строка 5 (status = "approved") — только внутри if amount > 0
- Use: строка 11 (конкатенация) и строка 14 (return status)

## Переменная: balance
- Def: строка 6 (balance = get_balance(user_id))
- Use: строка 7 (new_balance = balance - amount)

## Переменная: new_balance
- Def: строка 7 (new_balance = balance - amount)
- Use: строка 8 (update_balance(user_id, new_balance))

## Переменная: file
- Def: строка 12 (file = open("audit_log.txt", "w"))
- Use: строка 13 (file.write(log_entry))
- Нет close() → утечка ресурса
