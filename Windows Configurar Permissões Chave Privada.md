Verificar permissões
```bat
icacls "D:\FILES\ssh-key\id_rsa"
```

Tornar o usuário atual proprietário
```bat
takeown /F "D:\FILES\ssh-key\id_rsa"
```

Remover herança e manter permissões
```bat
icacls "D:\FILES\ssh-key\id_rsa" /Inheritance:d
```

Adicionar o usuário atual com permissões completa
```bat
icacls "D:\FILES\ssh-key\id_rsa" /c /t /Grant:r %username%:F
```

Remover permissões não administrativas
```bat
icacls "D:\FILES\ssh-key\id_rsa" /c /t /Remove:g "AUTORIDADE NT\Usuários autenticados" "BUILTIN\Usuários"
```

Verificar permissões
```bat
icacls "D:\FILES\ssh-key\id_rsa"
```