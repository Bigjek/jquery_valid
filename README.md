# Jquery валидация
Валидация поля url по доменам, ниже код который проверяет наличие (com, net, org).


        $('#domain_name').on('keyup', function(){
                var a = validateDomain($(this).val());
                    selectValid(a);
                }).focusout(function(){
                    var a = validateDomain($(this).val());
                    selectValid(a);
                });
                function selectValid (a) {
                    switch (a) {
                      case true:
                        $('.rez').text('valid domain')
                        break;
                      case false:
                        $('.rez').text('invalid domain')
                        break;
                    }
                }
                function validateDomain(the_domain){  
                   var reg = /^(http(s)?\:\/\/)?(www\.)?([a-zA-Z0-9]{1,}\.)?[a-zA-Z0-9]{2,}(\.(com|net|org))(\/)?([a-zA-Z0-9]{2,})?/;
                   return reg.test(the_domain);
                }
        });

