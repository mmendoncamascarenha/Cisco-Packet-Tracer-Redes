enable 
    
    configure terminal 
        !Configurações da VTY
        line vty 0 4 
            login local 
            password 123@senac
            logging synchronous
            exec-timeout 5 30
            transport input ssh 
            end
    write 

------------------------------------------------
(gateway)
enable 
    configure terminal 
        ip default-gateway 192.168.1.254 
        interface vlan 1
            description interface SVI do SW-01
            ip address 192.168.1.250 255.255.255.0
            no shutdown 
            end 

write 


---------------------------------------------- 
enable
    configure terminal
    ip domain-name senac.br
    crypto key generate rsa general-keys modulus 1024 
    ip ssh version 2
    ip ssh time-out 60
    ip ssh authentication-retries 2
    end
write   

