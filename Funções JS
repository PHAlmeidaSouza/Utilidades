<script type="text/javascript">
    //Função validar Email: onkeypress="return SomenteEmail();"
    function ValidaEmail(campo){
      if(campo.value!='' && campo.value!=null)
      {
      var f = campo.value
      if((f.indexOf("@") == -1) || (f.indexOf(".") == -1) && (f != '')){
      window.alert('E-mail inválido!');
      campo.focus();
      campo.value = '';
          }
      }
}

  //Função somente números: onkeypress="return somenteNumeros(event)" ----------------------
      function somenteNumeros(e) {
      var charCode = e.charCode ? e.charCode : e.keyCode;
      // charCode 8 = backspace   
      // charCode 9 = tab
      if (charCode != 8 && charCode != 9) {
      // charCode 48 equivale a 0   
      // charCode 57 equivale a 9
      if (charCode < 48 || charCode > 57) {
      return false;
      }
      }
}
  
  
    //Função somente letras com espaço onkeypress="return SomenteLetras()" ----------------------
      function SomenteLetras(){
      var tecla=(window.event)?event.keyCode:e.which;   
      if((tecla>64 && tecla<91)) return true;
      else{
      if (tecla>96 && tecla<123 || tecla==32 || tecla==227 || tecla==241 || tecla==0245 || tecla==195 || tecla==209 || tecla==213 || tecla==231 || tecla==225 || tecla== 233 || tecla== 237 || tecla== 243 || tecla== 250 || tecla== 193 || tecla== 201 || tecla== 205 || tecla== 211 || tecla== 218) return true;
      else  return false;
      }
  
}
  
  //Função para validar CPF: onBlur="ValidarCPF(this);" ----------------------
      function ValidarCPF (input) {
      s = input.value;
      filteredValues = ".-/"; 
      var i;
      var returnString = "";
      for (i = 0; i < s.length; i++) { 
      var c = s.charAt(i);
      if (filteredValues.indexOf(c) == -1) returnString += c;
      }
      if (returnString=='11111111111' || returnString=='22222222222' || 
      returnString=='33333333333' || returnString=='44444444444' || 
      returnString=='55555555555' || returnString=='66666666666' || 
      returnString=='77777777777' || returnString=='88888888888' || 
      returnString=='99999999999' || returnString=='00000000000' || returnString=='00000000191')
      {alert('CFP Inválido!'); input.value=""; return false;}
      if (returnString.length != 11) {sim=false}
      else {sim=true}
      if (sim ) {
      for (i=0;((i<=(returnString.length-1))&& sim); i++) {
      val = returnString.charAt(i)
      if ((val!="9")&&(val!="0")&&(val!="1")&&(val!="2")&&(val!="3")&&(val!="4")
      && (val!="5")&&(val!="6")&&(val!="7")&&(val!="8")) {sim=false}
      }
      if (sim) {
      soma = 0
      for (i=0;i<=8;i++) {
      val = eval(returnString.charAt(i))
      soma = soma + (val*(i+1))
}
      resto = soma % 11
      if (resto>9) dig = resto -10
      else  dig = resto
      if (dig != eval(returnString.charAt(9))) { sim=false }
      else { 
      soma = 0
      for (i=0;i<=7;i++) {
      val = eval(returnString.charAt(i+1))
      soma = soma + (val*(i+1))
      }
      soma = soma + (dig * 9)
      resto = soma % 11
      if (resto>9) dig = resto -10
      else  dig = resto
      if (dig != eval(returnString.charAt(10))) { sim = false }
      else {sim = true;}
}
      }
      }
      
      if (sim != true) {
      if (input.value != ''){
      alert("CPF Inválido! Digite novamente.");
      input.value = '';
      return false;
      }
      else{
      return false;  
      }	 
      }
}
  
  //Função para formatar mascára: onkeypress="formatar('###.###.###-##', this); return somenteNumeros(event)" ----------------------
      function formatar(mascara, documento){
      var i = documento.value.length;
      var saida = mascara.substring(0,1);
      var texto = mascara.substring(i)
      
      if (texto.substring(0,1) != saida){
      documento.value += texto.substring(0,1);
      
      }
}


    function limpa_formulário_cep() {
            //Limpa valores do formulário de cep.
            document.getElementById('inputRua').value=("");
            document.getElementById('inputBairro').value=("");
    }

    function meu_callback(conteudo) {
        if (!("erro" in conteudo)) {
            //Atualiza os campos com os valores.
            document.getElementById('inputRua').value=(conteudo.logradouro);
            document.getElementById('inputBairro').value=(conteudo.bairro);
        } //end if.
        else {
            //CEP não Encontrado.
            limpa_formulário_cep();
            alert("CEP não encontrado.");
        }
    }
        
    function pesquisacep(valor) {

    //Nova variável "cep" somente com dígitos.
    var cep = valor.replace(/\D/g, '');

    //Verifica se campo cep possui valor informado.
    if (cep != "") {

        //Expressão regular para validar o CEP.
        var validacep = /^[0-9]{8}$/;

        //Valida o formato do CEP.
        if(validacep.test(cep)) {

            //Preenche os campos com "..." enquanto consulta webservice.
            document.getElementById('inputRua').value="...";
            document.getElementById('inputBairro').value="...";

            //Cria um elemento javascript.
            var script = document.createElement('script');

            //Sincroniza com o callback.
            script.src = 'https://viacep.com.br/ws/'+ cep + '/json/?callback=meu_callback';

            //Insere script no documento e carrega o conteúdo.
            document.body.appendChild(script);

        } //end if.
        else {
            //cep é inválido.
            limpa_formulário_cep();
            alert("Formato de CEP inválido.");
        }
    } //end if.
    else {
        //cep sem valor, limpa formulário.
        limpa_formulário_cep();
    }
};
  
  var form = document.querySelector('.needs-validation');
  
  form.addEventListener('submit', function(event) {
  if (form.checkValidity() === false) {
    event.preventDefault();
    event.stopPropagation();
  }
    form.classList.add('was-validated');
  })
  
      //Função para preencher todos campos: onclick="confirmar()"
      function confirmar(){

      d = document.formCadastra;
      var s = new String();			
      var erro = false;

      s = '==== Para prosseguir, preencha os seguintes campos====\n\n';

      if (d.nomeCompleto.value=='' ){	s=s + '- Nome Completo \n'; erro=true}	
      if (d.dataNascimento.value=='' ){	s=s + '- Data de Nascimento \n'; erro=true}
      if (d.selectSexo.value=='' ){	s=s + '- Sexo \n'; erro=true}	
      if (d.estadoCivil.value=='' ){ s=s + '- Estado Civil \n'; erro=true}	
      if (d.inputCEP.value=='' ){	s=s + '- CEP \n'; erro=true}	
      if (d.inputRua.value=='' ){	s=s + '- Rua \n'; erro=true}
      if (d.inputBairro.value=='' ){	s=s + '- Bairro \n'; erro=true}	
      if (d.selectEstado.value=='' ){	s=s + '- Estado \n'; erro=true}
      if (d.selectCidade.value=='' ){	s=s + '- Cidade \n'; erro=true}
      if (d.inputEmail.value=='' ){	s=s + '- E-mail \n'; erro=true}	
      if (d.nomeMae.value=='' ){	s=s + '- Nome da Mãe \n'; erro=true}	
      if (d.nomePai.value=='' ){	s=s + '- Nome do Pai \n'; erro=true}
      if (d.inputCPF.value=='' ){	s=s + '- CPF \n'; erro=true}	
      if (d.inputRG.value=='' ){	s=s + '- RG \n'; erro=true}	
      if (d.telefoneResidencial.value=='' ){	s=s + '- Telefone Residencial \n'; erro=true}	
      if (d.telefoneCelular.value=='' ){	s=s + '- Telefone Celular \n'; erro=true}	
      
          
      if(erro) {alert(s);}

      else {
      d.hdnCadastra.value=1;
      window.alert('Formulário Cadastrado com Sucesso!')
      d.submit();
      }

}   
    //Função validar data: onblur="ValidaData(this, event);"
    function ValidaData(campo){
    var erro = true;
    if(campo.value != '')
    {
        var strData = campo.value;
        
        var dia = strData.substr(0,2);
        var mes = strData.substr(3,2);
        var ano = strData.substr(6,4);
        var datainteira = new String();
        datainteira = "";

        if(dia > 31)
        {
            alert("Dia inválido!");
            campo.value = "";
            return false;
        }
        datainteira = dia + '/';

        if(mes > 12)
        {
            alert("Mes inválido!");
            campo.value = "";
            return false;
        }

        datainteira  = datainteira  + mes + '/';
        if(ano < 1920 || ano>2023)
        {
            alert("Ano inválido!");
            campo.value = "";
            return false;
        }
        datainteira  = datainteira  + ano;
        if(mes == 02 && ano%4 == 0)
        {
            if(dia > 29)
            {
                alert("O mês de fevereiro em um ano bissexto so possui 29 dias!");
                campo.value = "";
                return false;
            }
        }

        if(mes == 02 && ano%4 != 0)
        {
            if(dia > 28)
            {
                alert("O mês de fevereiro so possui 28 dias!");
                campo.value = ""
                return false;
            }
        }

        if(mes != 01 || mes != 03 || mes != 05 || mes != 07 || mes != 08 || mes != 10 || mes != 12)
        {
            if(dia > 31)
            {
                alert("O Mês informado não possui 31 dias!")
                campo.value = ""
                return false;
            }
        }
        campo.value = datainteira;
    }
}
</script>
<script>
    const urlUF = 'https://servicodados.ibge.gov.br/api/v1/localidades/estados'
    const cidades = document.getElementById('selectCidade')
    const uf = document.getElementById('selectEstado')

    uf.addEventListener('change', async function(){
        const urlCidades = 'https://servicodados.ibge.gov.br/api/v1/localidades/estados/'+uf.value+'/municipios'
        const request = await fetch(urlCidades)
        const response = await request.json()
        console.log(response.length)

        let options = ''
        response.forEach(function(cidades){
            options += '<option>' +cidades.nome+'</option>'
        })
        cidades.innerHTML = options;
    })

    window.addEventListener('load', async ()=>{
        const request = await fetch(urlUF)
        const response = await request.json()
        response.sort((a, b) => a.nome.localeCompare(b.nome))

        const options = document.createElement("optgroup")
        options.setAttribute('label', 'UFs')
        response.forEach(function(uf){
            options.innerHTML += '<option>'+uf.sigla+'</option>'
        })
        uf.append(options)
    })
</script>
