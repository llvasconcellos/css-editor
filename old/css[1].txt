<%@LANGUAGE="vbscript"%>
<%
local = server.URLEncode(replace(replace(request.ServerVariables("PATH_TRANSLATED"),"\css.asp",""),request.ServerVariables("APPL_PHYSICAL_PATH"),""))
%>
<HTML>
	<HEAD>
		<TITLE>Edição de Atributos CSS</TITLE>
		<SCRIPT language="JavaScript" type="text/javascript">
			var i = 0;
			var id;
			var ultimo = '1';
			var div_filtro="";
			
			function tab(div, objeto){
				eval("div" + ultimo + ".style.visibility = \'hidden\';");
				eval("tab" + ultimo + ".style.backgroundImage = \"url(\'imagens/ababranca.gif\')\"");
				eval("div" + div + '.style.visibility = \'visible\';');
				objeto.style.backgroundImage = "url('imagens/abaazul.gif')";
				ultimo = div;
				if(div_filtro != ""){
					eval(div_filtro + ".style.visibility = 'hidden'");
				}
				if (div == "7"){
					if (div_filtro != ""){
						eval(div_filtro + ".style.visibility = 'visible'");
					}
				}
			}
		</SCRIPT>
		<STYLE type="text/css">
			.Label {
				background-Image:  url('imagens/ababranca.gif');
				background-repeat: no-repeat;
				cursor: pointer;
				font-family: Arial;
				color: #000000;
				font-size: 13px;
				filter: Alpha(Opacity=50);
			}
			body {
				background-color: white;
				margin: 0px;
				padding: 0px;
			}
			.label2{
				font-weight: bold;
				font-family: Arial, Helvetica, sans-serif;
				font-size: 12px;
				color: #4A93EC;
				text-align: right;
			}
			.label3{
				font-weight: bold;
				font-family: Arial, Helvetica, sans-serif;
				font-size: 12px;
				color: #4A93EC;
			}
			.conteudo {
				background-color: transparent;
			}
			.popup{
				outline: red solid thin;
				color: #666666;
				height: 20px;
				font-family: Arial, Helvetica, sans-serif;
				font-size: 12px;
				background-color: #E2FFFF;
				border: solid 1px #0F5EBF;
			}
			.campo{
				color: #666666;
				height: 20px;
				font-family: Arial, Helvetica, sans-serif;
				font-size: 12px;
				border: solid 1px #0F5EBF;
				FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);
			}
			.texto{
				color: #666666;
				font-family: Arial, Helvetica, sans-serif;
				font-size: 10px;
			}
		-->
		</STYLE>
</HEAD>

<BODY scroll="no">
<FORM name="css">
	<TABLE cellspacing="0" style="left: 0px; top:0px; position: absolute; width: 100%; z-index: 10;" cols="9">
		<TR>
			<td></td>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('1', this);" id="tab1" style="filter: Alpha(Opacity=50); background-Image:  url('imagens/abaazul.gif'); background-repeat: no-repeat; cursor: pointer; font-family: Arial; color: #000000; font-size: 13px;" width="99" height="27" align="center"><b>Texto</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('2', this);" id="tab2" width="99" class="Label" align="center"><b>Fundo</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('3', this);" id="tab3" width="99" class="Label" align="center"><b>Borda</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('4', this);" id="tab4" width="99" class="Label" align="center"><b>Alinhamento</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('5', this);" id="tab5" width="99" class="Label" align="center"><b>Margens</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('6', this);" id="tab6" width="99" class="Label" align="center"><b>Posição</b></TD>
			<TD onMouseOver="this.style.filter = 'Alpha(Opacity=100)';" onMouseOut="this.style.filter = 'Alpha(Opacity=50)';" onClick="tab('7', this);" id="tab7" width="99" class="Label" align="center"><b>Outros</b></TD>
			<td></td>
		</TR>
		<tr>
			<td height="18" colspan="9" style="background-Image:  url('imagens/linhaazul.gif');"></td>
		</tr>
	</TABLE>
<TABLE width="100%" cellpadding="0" border="0" cellspacing="0" cols="3" height="100%" style="position: absolute; z-index: 0; top: 3px;">
	<TR>
		<TD width="24"  style="height: 24px; background-attachment: fixed; background-repeat: no-repeat; background-position: left top;"></TD>
		<TD  width="100%" style="background-attachment: fixed; background-repeat: repeat-x; background-position: left top;"></TD>
		<TD width="24"></TD>
	</TR>
	<TR height="100%">
		<TD background="imagens/borda_lateral_esquerda.gif"></TD>
		<TD style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#FFFFFF,endColorStr=#F5FFFF);"></TD>
		<TD background="imagens/borda_lateral_direita.gif"></TD>
	</TR>
	<TR>
		<TD background="imagens/canto_inferior_esquerdo.gif" width="24" height="26"></TD>
		<TD background="imagens/borda_inferior.gif" height="26"></TD>
		<TD background="imagens/canto_inferior_direito.gif" width="24" height="26"></TD>
	</TR>
</TABLE>
<div id="div1" class="conteudo" style="position: absolute; top: 13%; left: 4%; width: 91%;">
			<table cellpadding="0"  width="70%">
				<tr>
					<td class="label2" style="width: 30%">Fontes</td>
					<td style="width: 70%">
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT onChange="teste.style.fontFamily = this.value;" style="width: 100%;" class="popup">
										<option value=""></option>
										<OPTION value="Arial, Helvetica, sans-serif">Arial, Helvetica, sans-serif</OPTION>
										<OPTION value="Times New Roman, Times, serif">Times New Roman, Times, serif</OPTION>
										<OPTION value="Courier New, Courier, mono">Courier New, Courier, mono</OPTION>
										<OPTION value="Georgia, Times New Roman, Times, serif">Georgia, Times New Roman, Times, serif</OPTION>
										<OPTION value="Verdana, Arial, Helvetica, sans-serif">Verdana, Arial, Helvetica, sans-serif</OPTION>
										<OPTION value="Geneva, Arial, Helvetica, sans-serif">Geneva, Arial, Helvetica, sans-serif</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Tamanho</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td style="width: 33%;">
									<SELECT class="popup" onChange="eval(this.value); fsizetxt.value=''; fontsizetype.selectedIndex = 0;" id="fontsize" style="width: 100%;">
										<OPTION value="teste.style.fontSize=''"></option>
										<OPTION value="teste.style.fontSize='8'">8</OPTION>
										<OPTION value="teste.style.fontSize='9'">9</OPTION>
										<OPTION value="teste.style.fontSize='10'">10</OPTION>
										<OPTION value="teste.style.fontSize='12'">12</OPTION>
										<OPTION value="teste.style.fontSize='14'">14</OPTION>
										<OPTION value="teste.style.fontSize='16'">16</OPTION>
										<OPTION value="teste.style.fontSize='18'">18</OPTION>
										<OPTION value="teste.style.fontSize='24'">24</OPTION>
										<OPTION value="teste.style.fontSize='36'">36</OPTION>
										<OPTION value="teste.style.fontSize='xx-small'">xx-small</OPTION>
										<OPTION value="teste.style.fontSize='x-small'">x-small</OPTION>
										<OPTION value="teste.style.fontSize='small'">small</OPTION>
										<option value="teste.style.fontSize='medium'">medium</option>
										<OPTION value="teste.style.fontSize='large'">large</OPTION>
										<OPTION value="teste.style.fontSize='x-large'">x-large</OPTION>
										<OPTION value="teste.style.fontSize='xx-large'">xx-large</OPTION>
										<OPTION value="teste.style.fontSize='smaller'">smaller</OPTION>
										<OPTION value="teste.style.fontSize='larger'">larger</OPTION>
									</SELECT>
								</td>
								<td style="width: 33%;">
									<INPUT type="text" onBlur="if (this.value != ''){ 
																	eval('teste.style.fontSize=' + '\'' + this.value + css.fontsizetype.value + '\''); 
																}
																else { 
																	teste.style.fontSize = '';
																	fontsizetype.selectedIndex = 0;
																}" id="fsizetxt" onKeyDown="if (css.fontsizetype.value == '') css.fontsizetype.selectedIndex = 1; if (css.fontsize.selectedIndex != 0) css.fontsize.selectedIndex = 0;"  style="width: 100%;" class="campo">
								</td>
								<td style="width: 33%;">
									<SELECT class="popup" name="fontsizetype" style="width: 100%;" onChange="if (fsizetxt.value != '') eval('teste.style.fontSize=' + '\'' + fsizetxt.value + this.value + '\'');">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Estilo</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT class="popup" onChange="eval(this.value);" style="width: 100%;">
										<option value="teste.style.fontStyle=''"></option>
										<OPTION value="teste.style.fontStyle='normal'">Normal</OPTION>
										<OPTION value="teste.style.fontStyle='italic'">Itálico</OPTION>
										<OPTION value="teste.style.fontStyle='oblique'">Oblíquo</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>	
					</td>
				</tr>
				<tr>
					<td class="label2">Espaço entre Linhas</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td  style="width: 60%;">
									<INPUT type="text" class="campo" id="lh" onBlur="if (this.value != '') teste.style.lineHeight = this.value + lhpopup.value; else lhpopup.selectedIndex = 0;" style="width: 100%;" onKeyDown="if (lhpopup.selectedIndex == 0) lhpopup.selectedIndex = 1;">
								</td>
								<td  style="width: 40%;">
									<SELECT class="popup" name="lhpopup" style="width: 100%;" id="lhpopup" onChange="if (lh.value != '') teste.style.lineHeight = lh.value + this.value;">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Decoração</td>
					<td>
						<table style="width: 100%">
							<tr>
								<td align="right" class="texto">Sublinhado</td>
								<td align="right"><INPUT id="sublinhado" type="checkbox" onClick="txtdecor.checked = false; if (this.checked) teste.style.textDecorationUnderline = true; else teste.style.textDecorationUnderline = false;"></td>	
								<td align="right" class="texto">Sobrelinhado</td>
								<td align="right"><INPUT id="sobrelinhado" type="checkbox" onClick="txtdecor.checked = false; if (this.checked) teste.style.textDecorationOverline = true; else teste.style.textDecorationOverline = false;"></td>
							</tr>
							<tr>	
								<td align="right" class="texto">Riscado</td>
								<td align="right"><INPUT id="riscado" type="checkbox" onClick="txtdecor.checked = false; if (this.checked) teste.style.textDecorationLineThrough = true; else teste.style.textDecorationLineThrough = false;"></td>
								<td align="right" class="texto">Piscar (Netscape)</td>
								<td align="right"><INPUT id="piscar" type="checkbox" onClick="txtdecor.checked = false; if (this.checked) teste.style.textDecorationBlink = true; else teste.style.textDecorationBlink = false;"></td>
							</tr>
							<tr>
								<td align="right" class="texto">Sem</td>
								<td align="right"><INPUT id="txtdecor" type="checkbox" onClick="if (this.checked) { teste.style.textDecorationNone = true; css.riscado.checked = false; css.piscar.checked = false; css.sublinhado.checked = false; css.sobrelinhado.checked = false;} else teste.style.textDecorationNone = false;"></td>						
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Negrito</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT class="popup" onChange="eval(this.value);" style="width: 100%;">
										<option value="teste.style.fontWeight=''"></option>
										<OPTION value="teste.style.fontWeight='normal'">Normal</OPTION>
										<OPTION value="teste.style.fontWeight='bold'">Negrito</OPTION>
										<OPTION value="teste.style.fontWeight='bolder'">Super Negrito</OPTION>
										<OPTION value="teste.style.fontWeight='Lighter'">Light</OPTION>
										<OPTION value="teste.style.fontWeight='100'">100</OPTION>
										<OPTION value="teste.style.fontWeight='200'">200</OPTION>
										<OPTION value="teste.style.fontWeight='300'">300</OPTION>
										<OPTION value="teste.style.fontWeight='400'">400</OPTION>
										<OPTION value="teste.style.fontWeight='500'">500</OPTION>
										<OPTION value="teste.style.fontWeight='600'">600</OPTION>
										<OPTION value="teste.style.fontWeight='700'">700</OPTION>
										<OPTION value="teste.style.fontWeight='800'">800</OPTION>
										<OPTION value="teste.style.fontWeight='900'">900</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Variação</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT class="popup" onChange="eval(this.value);" style="width: 100%;">
										<option value="teste.style.fontVariant=''"></option>
										<OPTION value="teste.style.fontVariant='normal'">Normal</OPTION>
										<OPTION value="teste.style.fontVariant='small-caps'">Maiúculas Pequenas</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Transformação</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT class="popup" onChange="eval(this.value);" style="width: 100%;">
										<option value="teste.style.textTransform=''"></option>
										<OPTION value="teste.style.textTransform='capitalize'">Capitalize</OPTION>
										<OPTION value="teste.style.textTransform='uppercase'">Maiúculas</OPTION>
										<OPTION value="teste.style.textTransform='lowercase'">Minúsculas</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Cor</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td style="width: 88%"><input type="text" name="colortxt" onBlur="javascript: teste.style.color = this.value;" style="width: 100%" class="campo"></td>
								<td style="width: 12%"><img onClick="javascript: selecionacor('txt');" style="cursor: pointer;" src="imagens/cores.gif"></td>
							</tr>
						</table>
					</td>
				</tr>
			</table>
		</div>
		<div class="conteudo" id="div2" style="visibility: hidden; position: absolute; top: 13%; left: 4%; width: 91%;">
			<TABLE width="70%" cellpadding="0" bor>
				<tr>
					<td width="25%" class="label2">Cor</td>
					<td width="75%">
						<table style="width: 100%;">
							<tr>
								<td style="width: 80%;"><input type="text" name="colornum" onBlur="javascript: teste.style.backgroundColor = this.value;" style="width: 100%;" class="campo"></td>
								<td style="width: 20%;"><img onClick="javascript: selecionacor('bg');" style="cursor: pointer;" src="imagens/cores2.gif"></td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Imagem</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td style="width: 80%;"><input type="text" name="imgpath" id="imgpath" style="width: 100%;" onBlur="javascript: teste.style.backgroundImage = 'url(\'' + this.value + '\)';" class="campo"></td>
								<td style="width: 20%;"><img onClick="arq(imgpath.form.name + '.' + imgpath.name);" style="cursor: pointer;" src="imagens/procurar.gif"></td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Repetição</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT onChange="eval(this.value);" style="width: 100%;" class="popup">
										<OPTION value="teste.style.backgroundRepeat=''"></option>
										<OPTION value="teste.style.backgroundRepeat='no-repeat'">Sem Repetição</OPTION>
										<OPTION value="teste.style.backgroundRepeat='repeat'">Repetição</OPTION>
										<OPTION value="teste.style.backgroundRepeat='repeat-x'">Repetição na Horizontal</OPTION>
										<OPTION value="teste.style.backgroundRepeat='repeat-y'">Repetição na Vertical</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
					</td>
				</tr>
				<tr>
					<td class="label2">Movimentação</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td>
									<SELECT onChange="eval(this.value);" style="width: 100%;" class="popup">
										<option value="teste.style.backgroundAttachment=''"></option>
										<OPTION value="teste.style.backgroundAttachment='fixed'">Fixo</OPTION>
										<OPTION value="teste.style.backgroundAttachment='scroll'">Rolar</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Posição Horizontal</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td style="width: 33%;">
									<SELECT onChange="javascript: bgposition1(this.value); bgpos1txt.value=''; bgpos1type.selectedIndex = 0;" id="bgpos1"  style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="center">Centralizado</OPTION>
										<OPTION value="left">Esquerdo</OPTION>
										<OPTION value="right">Direito</OPTION>
									</SELECT>
								</td>
								<td style="width: 33%;">
									<INPUT type="text" onBlur="if (this.value != ''){
																	bgposition1(this.value + bgpos1type.value); 
																	bgpos1.selectedIndex = 0;
																}
																else {
																	bgposition1(''); 
																	bgpos1type.selectedIndex = 0;
																}"  onKeyDown="if (bgpos1type.selectedIndex == 0) bgpos1type.selectedIndex = 1;"id="bgpos1txt"  style="width: 100%;" class="campo">
								</td>
								<td style="width: 33%;">
									<SELECT name="bgpos1type" style="width: 100%;" onChange="if (bgpos1txt.value != '') bgposition1(bgpos1txt.value + this.value);" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Posição Vertical</td>
					<td>
						<table style="width: 100%;">
							<tr>
								<td style="width: 33%;">
									<SELECT onChange="javascript: bgposition2(this.value); bgpos2txt.value=''; bgpos2type.selectedIndex = 0;" id="bgpos2"  style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="center">Centralizado</OPTION>
										<OPTION value="top">Topo</OPTION>
										<OPTION value="bottom">Em Baixo</OPTION>
									</SELECT>
								</td>
								<td style="width: 33%;">
									<INPUT type="text" onBlur="if (this.value != ''){
																	bgposition2(this.value + bgpos2type.value); 
																	bgpos2.selectedIndex = 0;
																}
																else {
																	bgposition2(''); 
																	bgpos2type.selectedIndex = 0;
																}"  onKeyDown="if (bgpos2type.selectedIndex == 0) bgpos2type.selectedIndex = 1;"id="bgpos2txt"  style="width: 100%;" class="campo">
								</td>
								<td style="width: 33%;">
									<SELECT name="bgpos2type" style="width: 100%;" onChange="if (bgpos2txt.value != '') bgposition2(bgpos2txt.value + this.value);" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
			</TABLE>
		</div>
		<div class="conteudo" id="div3" style="visibility: hidden; position: absolute; top: 13%; left: 4%; width: 91%;">
			<TABLE width="70%" cellpadding="2">
				<tr>
					<td valign="bottom">
						<table cellpadding="0" width="100%">
							<tr>
								<td colspan="2" class="label3" align="center">Estilo da Borda</td>
							</tr>
							<tr>
								<td colspan="2" align="center" class="label2">
									<INPUT id="brdrstyle" type="checkbox" onClick="if (this.checked){
																						css.bs2.selectedIndex = css.bs1.selectedIndex;
																						css.bs3.selectedIndex = css.bs1.selectedIndex;
																						css.bs4.selectedIndex = css.bs1.selectedIndex;
																						teste.style.borderBottomStyle = css.bs1.value;
																						teste.style.borderLeftStyle = css.bs1.value;
																						teste.style.borderRightStyle = css.bs1.value;
																						css.bs2.disabled = true;
																						css.bs3.disabled = true;
																						css.bs4.disabled = true;
																					}
																					else{
																						css.bs2.disabled = false;
																						css.bs3.disabled = false;
																						css.bs4.disabled = false;
																					}" checked>Igual para todos</td>
							</tr>
							<tr>
								<td width="20%" align="right"  class="label2">Superior</td>
								<td width="80%">
									<SELECT onChange="  eval('teste.style.borderTopStyle=' + '\'' + this.value + '\'');
														if(css.brdrstyle.checked){
															css.bs2.selectedIndex = this.selectedIndex;
															css.bs3.selectedIndex = this.selectedIndex;
															css.bs4.selectedIndex = this.selectedIndex;
															eval('teste.style.borderBottomStyle=' + '\'' + this.value + '\'');
															eval('teste.style.borderRightStyle=' + '\'' + this.value + '\'');
															eval('teste.style.borderLeftStyle=' + '\'' + this.value + '\'');																	
														}" name="bs1" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="dotted">Pontilhado</OPTION>
										<OPTION value="dashed">Tracejado</OPTION>
										<OPTION value="solid">Solido</OPTION>
										<OPTION value="double">Dupla</OPTION>
										<OPTION value="groove">GROOVE</OPTION>
										<OPTION value="ridge">RIDGE</OPTION>
										<OPTION value="inset">inset</OPTION>
										<OPTION value="outset">outset</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Inferior</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderBottomStyle=' + '\'' + this.value + '\'');" name="bs2" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="dotted">Pontilhado</OPTION>
										<OPTION value="dashed">Tracejado</OPTION>
										<OPTION value="solid">Solido</OPTION>
										<OPTION value="double">Dupla</OPTION>
										<OPTION value="groove">GROOVE</OPTION>
										<OPTION value="ridge">RIDGE</OPTION>
										<OPTION value="inset">inset</OPTION>
										<OPTION value="outset">outset</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Direito</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderRightStyle=' + '\'' + this.value + '\'');" name="bs3" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="dotted">Pontilhado</OPTION>
										<OPTION value="dashed">Tracejado</OPTION>
										<OPTION value="solid">Solido</OPTION>
										<OPTION value="double">Dupla</OPTION>
										<OPTION value="groove">GROOVE</OPTION>
										<OPTION value="ridge">RIDGE</OPTION>
										<OPTION value="inset">inset</OPTION>
										<OPTION value="outset">outset</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Esquerdo</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderLeftStyle=' + '\'' + this.value + '\'');" name="bs4" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="dotted">Pontilhado</OPTION>
										<OPTION value="dashed">Tracejado</OPTION>
										<OPTION value="solid">Solido</OPTION>
										<OPTION value="double">Dupla</OPTION>
										<OPTION value="groove">GROOVE</OPTION>
										<OPTION value="ridge">RIDGE</OPTION>
										<OPTION value="inset">inset</OPTION>
										<OPTION value="outset">outset</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
					<td>
						<table cellpadding="0" width="100%">
							<tr>
								<td colspan="2" class="label3" align="center">Cor da Borda</td>
							</tr>
							<tr>
								<td colspan="2" align="center" class="label2">
									<INPUT id="brdrcolor" name="brdrcolor" type="checkbox" onClick="if (!checked){
																										css.brdrcolor2.disabled = false;
																										css.brdrcolor3.disabled = false;
																										css.brdrcolor4.disabled = false;
																										css.brdrcolorbutton2.disabled = false;
																										css.brdrcolorbutton3.disabled = false;
																										css.brdrcolorbutton4.disabled = false;
																										}
																									else{
																										css.brdrcolor2.disabled = true;
																										css.brdrcolor3.disabled = true;
																										css.brdrcolor4.disabled = true;
																										css.brdrcolorbutton2.disabled = true;
																										css.brdrcolorbutton3.disabled = true;
																										css.brdrcolorbutton4.disabled = true;
																										css.brdrcolor2.value = css.brdrcolor1.value;
																										css.brdrcolor3.value = css.brdrcolor1.value;
																										css.brdrcolor4.value = css.brdrcolor1.value;
																										teste.style.borderTopColor = css.brdrcolor1.value;
																										teste.style.borderBottomColor = css.brdrcolor1.value;
																										teste.style.borderRightColor = css.brdrcolor1.value;
																										teste.style.borderLeftColor = css.brdrcolor1.value;
																										}" checked>Igual para todos</td>
							</tr>
							<tr>
								<td width="87%"><input type="text" name="brdrcolor1" size="8" onBlur="javascript: teste.style.borderTopColor = this.value;
																							if(css.brdrcolor.checked){
																								teste.style.borderBottomColor = this.value;
																								teste.style.borderLeftColor = this.value;
																								teste.style.borderRightColor = this.value;
																								css.brdrcolor2.value = this.value;
																								css.brdrcolor3.value = this.value;
																								css.brdrcolor4.value = this.value;
																							}"
																				onKeyUp="	if(css.brdrcolor.checked){
																							css.brdrcolor2.value = this.value;
																							css.brdrcolor3.value = this.value;
																							css.brdrcolor4.value = this.value;
																							}" style="width: 100%;" class="campo"></td>
								<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="brdrcolorbutton1" onClick="javascript: selecionacor('brdrcolor1');"></td>
							</tr>
							<tr>
								<td><input type="text" class="campo" name="brdrcolor2" onBlur="javascript: teste.style.borderBottomColor = this.value;" size="8" disabled style="width: 100%;"></td>
								<td><img src="imagens/cores.gif" style="cursor: pointer;" name="brdrcolorbutton2" onClick="javascript: selecionacor('brdrcolor2');" disabled></td>
							</tr>
							<tr>
								<td><input type="text" class="campo" name="brdrcolor3" onBlur="javascript: teste.style.borderRightColor = this.value;" size="8" disabled style="width: 100%;"></td>
								<td><img src="imagens/cores.gif" style="cursor: pointer;" name="brdrcolorbutton3" onClick="javascript: selecionacor('brdrcolor3');" disabled></td>
							</tr>
							<tr>
								<td><input type="text" class="campo" name="brdrcolor4" onBlur="javascript: teste.style.borderLeftColor = this.value;" size="8" disabled style="width: 100%;"></td>
								<td><img src="imagens/cores.gif" style="cursor: pointer;" name="brdrcolorbutton4" onClick="javascript: selecionacor('brdrcolor4');" disabled></td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td colspan="2">
						<table cellpadding="0" width="50%">
							<tr>
								<td colspan="4" class="label3" align="center">Largura da Borda</td>
							</tr>
							<tr>
								<td colspan="4" align="center" class="label2">
									<INPUT id="brdrwidth" type="checkbox" onClick="if (!checked){ 
																						css.brdrwidth2.disabled = false;
																						css.brdrwidth3.disabled = false;
																						css.brdrwidth4.disabled = false;
																						css.brbottxt.disabled = false;
																						css.brlefttxt.disabled = false;
																						css.brrighttxt.disabled = false;
																						css.brdbotwdt.disabled = false;
																						css.brdrigwdt.disabled = false;
																						css.brdleftwdt.disabled = false;
																					} 
																					else {
																						css.brdrwidth2.selectedIndex = css.brdrwidth1.selectedIndex;
																						css.brdrwidth3.selectedIndex = css.brdrwidth1.selectedIndex;
																						css.brdrwidth4.selectedIndex = css.brdrwidth1.selectedIndex;
																						teste.style.borderBottomWidth = css.brdrwidth1.value;
																						teste.style.borderRightWidth = css.brdrwidth1.value;
																						teste.style.borderLeftWidth = css.brdrwidth1.value;
																						css.brdrwidth2.disabled = true;
																						css.brdrwidth3.disabled = true;
																						css.brdrwidth4.disabled = true;
																						css.brbottxt.disabled = true;
																						css.brlefttxt.disabled = true;
																						css.brrighttxt.disabled = true;
																						css.brdbotwdt.disabled = true;
																						css.brdrigwdt.disabled = true;
																						css.brdleftwdt.disabled = true;
																						if (css.brdrwidth1.value == '' && css.brtoptxt.value != ''){
																							css.brbottxt.value = css.brtoptxt.value;
																							css.brrighttxt.value = css.brtoptxt.value;
																							css.brlefttxt.value = css.brtoptxt.value;
																							css.brdbotwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																							css.brdrigwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																							css.brdleftwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																							eval('teste.style.borderTopWidth=\'' + brtoptxt.value + brdtopwdt.value + '\'');
																							eval('teste.style.borderBottomWidth=\'' + brtoptxt.value + brdtopwdt.value + '\'');
																							eval('teste.style.borderRightWidth=\'' + brtoptxt.value + brdtopwdt.value + '\'');
																							eval('teste.style.borderLeftWidth=\'' + brtoptxt.value + brdtopwdt.value + '\'');
																						}
																					}" checked>Igual para todos</td>
							</tr>
							<tr>
								<td width="15%" align="right" class="label2">Superior</td>
								<td width="30%">
									<SELECT onChange=	"eval('teste.style.borderTopWidth=\'' + this.value + '\'');
															if (css.brdrwidth.checked){
																css.brdrwidth2.selectedIndex = css.brdrwidth1.selectedIndex;
																css.brdrwidth3.selectedIndex = css.brdrwidth1.selectedIndex;
																css.brdrwidth4.selectedIndex = css.brdrwidth1.selectedIndex;
																teste.style.borderBottomWidth = css.brdrwidth1.value;
																teste.style.borderRightWidth = css.brdrwidth1.value;
																teste.style.borderLeftWidth = css.brdrwidth1.value;
															}
															if (this.value != ''){
																css.brtoptxt.disabled = true;
																css.brbottxt.disabled = true;
																css.brrighttxt.disabled = true;
																css.brlefttxt.disabled = true;
																css.brtoptxt.value = '';
																css.brbottxt.value = '';
																css.brrighttxt.value = '';
																css.brlefttxt.value = '';
																css.brdtopwdt.selectedIndex = 0;
																css.brdbotwdt.selectedIndex = 0;
																css.brdrigwdt.selectedIndex = 0;
																css.brdleftwdt.selectedIndex = 0;
															}
															if (this.value == ''){
																css.brtoptxt.disabled = false;
																if (!css.brdrwidth.checked){
																	css.brbottxt.disabled = false;
																	css.brrighttxt.disabled = false;
																	css.brlefttxt.disabled = false;
																	css.brdbotwdt.disabled = false;
																	css.brdrigwdt.disabled = false;
																	css.brdleftwdt.disabled = false;
																}
															}
														" name="brdrwidth1" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="thin">Fino</OPTION>
										<OPTION value="medium">Médio</OPTION>
										<OPTION value="thick">Grosso</OPTION>
									</SELECT>
								</td>
								<td width="30%">
									<input type="text" name="brtoptxt" size="3" onKeyUp="if (css.brdrwidth.checked){
																							css.brbottxt.value = this.value;
																							css.brrighttxt.value = this.value;
																							css.brlefttxt.value = this.value;
																						}"
																				 onBlur="if (this.value != '') {
																				 			eval('teste.style.borderTopWidth=\'' + this.value + brdtopwdt.value + '\'');
																							if (css.brdrwidth.checked){
																								eval('teste.style.borderBottomWidth=\'' + this.value + brdtopwdt.value + '\'');
																								eval('teste.style.borderRightWidth=\'' + this.value + brdtopwdt.value + '\'');
																								eval('teste.style.borderLeftWidth=\'' + this.value + brdtopwdt.value + '\'');
																							}
																						}
																						else {
																							brdtopwdt.selectedIndex = 0;
																							if (css.brdrwidth.checked){
																								css.brdbotwdt.selectedIndex = 0;
																								css.brdrigwdt.selectedIndex = 0;
																								css.brdleftwdt.selectedIndex = 0;	
																							}
																						}" onKeyDown="brdtopwdt.selectedIndex = 1;
																									  if (css.brdrwidth.checked){
																											css.brdbotwdt.selectedIndex = 1;
																											css.brdrigwdt.selectedIndex = 1;
																											css.brdleftwdt.selectedIndex = 1;
																									   }" style="width: 100%;" class="campo">
								</td>
								<td width="25%">
									<SELECT name="brdtopwdt" onChange="if (css.brtoptxt.value != ''){
																			eval('teste.style.borderTopWidth=\'' + css.brtoptxt.value + this.value + '\'');
																			if (css.brdrwidth.checked){
																				css.brdbotwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																				css.brdrigwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																				css.brdleftwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																				eval('teste.style.borderBottomWidth=\'' + css.brtoptxt.value + brdbotwdt.value + '\'');
																				eval('teste.style.borderRightWidth=\'' + css.brtoptxt.value + brdrigwdt.value + '\'');
																				eval('teste.style.borderLeftWidth=\'' + css.brtoptxt.value + brdleftwdt.value + '\'');
																			}
																		}
																		else {
																			if (css.brdrwidth.checked){
																				css.brdbotwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																				css.brdrigwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																				css.brdleftwdt.selectedIndex = css.brdtopwdt.selectedIndex;
																			}
																		}" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Inferior</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderBottomWidth=\'' + this.value + '\'');" name="brdrwidth2" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="thin">Fino</OPTION>
										<OPTION value="medium">Médio</OPTION>
										<OPTION value="thick">Grosso</OPTION>
									</SELECT>
								</td>
								<td>
									<input type="text" style="width: 100%;" name="brbottxt" size="3" disabled onBlur="eval('teste.style.borderBottomWidth=\'' + this.value + brdbotwdt.value + '\'');" onKeyDown="if (brdbotwdt.selectedIndex == 0) brdbotwdt.selectedIndex = 1;" class="campo">
								</td>
								<td>
									<SELECT name="brdbotwdt" disabled style="width: 100%;" onChange="if (brbottxt.value != ''){
																									 	eval('teste.style.borderBottomWidth=\'' + brbottxt.value + this.value + '\'');	
																									 }" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Direito</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderRightWidth=\'' + this.value + '\'');" name="brdrwidth3" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="thin">Fino</OPTION>
										<OPTION value="medium">Médio</OPTION>
										<OPTION value="thick">Grosso</OPTION>
									</SELECT>
								</td>
								<td>
									<input type="text" class="campo" style="width: 100%;" name="brrighttxt" size="3" disabled onBlur="teste.style.borderRightWidth = this.value + brdrigwdt.value;" onKeyDown="if (brdrigwdt.selectedIndex == 0) brdrigwdt.selectedIndex = 1;">
								</td>
								<td>
									<SELECT class="popup" name="brdrigwdt" disabled style="width: 100%;" onChange="if (brrighttxt.value != '') teste.style.borderRightWidth = brrighttxt.value + this.value;">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td align="right" class="label2">Esquerdo</td>
								<td>
									<SELECT class="popup" onChange="eval('teste.style.borderLeftWidth=\'' + this.value + '\'');" name="brdrwidth4" disabled style="width: 100%;">
										<OPTION value=""></OPTION>
										<OPTION value="thin">Fino</OPTION>
										<OPTION value="medium">Médio</OPTION>
										<OPTION value="thick">Grosso</OPTION>
									</SELECT>
								</td>
								<td>
									<input type="text" class="campo" style="width: 100%;" name="brlefttxt" size="3" disabled onBlur="teste.style.borderLeftWidth = this.value + brdleftwdt.value;" onKeyDown="if (brdleftwdt.selectedIndex == 0) brdleftwdt.selectedIndex = 1;">
								</td>
								<td>
									<SELECT name="brdleftwdt" disabled style="width: 100%;" onChange="if (brlefttxt.value != '') teste.style.borderRightWidth = brlefttxt.value + this.value;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
			</TABLE>
		</div>
		<div class="conteudo" id="div4" style="visibility: hidden; position: absolute; top: 13%; left: 4%; width: 91%;">
			<TABLE width="70%" cellpadding="0">
				<tr>
					<td class="label2" width="25%">Alinhamento Vertical</td>
					<td width="25%">
						<SELECT onChange="eval('teste.style.verticalAlign=' + '\'' + this.value + '\'');
											if (this.value != ''){
												css.vrtaligntxt.value = '';
												css.vlva.selectedIndex = 0;
												css.vrtaligntxt.disabled = true;
												css.vlva.disabled = true;
											}
											else{
												css.vrtaligntxt.disabled = false;
												css.vlva.disabled = false;
											}" name="va" style="width: 100%" class="popup">
							<option value=""></option>
							<OPTION value="baseline">Linha Base</OPTION>
							<OPTION value="sub">Sub</OPTION>
							<OPTION value="super">Super</OPTION>
							<OPTION value="top">Superior</OPTION>
							<OPTION value="texttop">Alinhado c/ Texto Acima</OPTION>
							<OPTION value="middle">Meio</OPTION>
							<OPTION value="bottom">Em Baixo</OPTION>
							<OPTION value="textbottom">Alinhado c/ Texto Abaixo</OPTION>
						</SELECT>
					</td>
					<td width="25%">
						<INPUT type="text" onBlur="if (this.value != ''){
														eval('teste.style.verticalAlign=' + '\'' + this.value + css.vlva.value + '\'');
														css.va.selectedIndex = 0;
														css.va.disabled = true;
													}
													else{
														css.va.disabled = false;
													}" id="vrtaligntxt" style="width: 100%" class="campo">
					</td>
					<td width="25%">
						<SELECT name="vlva" onChange="eval('teste.style.verticalAlign=' + '\'' + vrtaligntxt.value + this.value + '\'');" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="px">Pixels</OPTION>
							<OPTION value="pt">Pontos</OPTION>
							<OPTION value="in">Poleg.</OPTION>
							<OPTION value="cm">Cm</OPTION>
							<OPTION value="mm">MM</OPTION>
							<OPTION value="pc">Picas</OPTION>
							<OPTION value="em">EMS</OPTION>
							<OPTION value="ex">EXS</OPTION>
							<OPTION value="%">%</OPTION>
						</SELECT>
					</td>
				</tr>
				<tr>
					<td class="label2">Alinhamento Texto</td>
					<td colspan="3">
						<SELECT onChange="eval(this.value);" style="width: 100%" class="popup">
							<option value="teste.style.textAlign=''"></option>
							<OPTION value="teste.style.textAlign='left'">Esquerda</OPTION>
							<OPTION value="teste.style.textAlign='right'">Direita</OPTION>
							<OPTION value="teste.style.textAlign='center'">Centralizado</OPTION>
							<OPTION value="teste.style.textAlign='justify'">Justificado</OPTION>
						</SELECT>
					</td>
				</tr>
				<tr>
					<td class="label2" style="font-size: 10px;">Espaço entre Palavras</td>
					<td>
						<SELECT onChange="eval('teste.style.wordSpacing=' + '\'' + this.value + '\'');
											if (this.value != ''){
												css.wstxt.value = '';
												css.vlws.selectedIndex = 0;
												css.wstxt.disabled = true;
												css.vlws.disabled = true;
											}
											else{
												css.wstxt.disabled = false;
												css.vlws.disabled = false;
											}" name="ws" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="Normal">Normal</OPTION>
						</SELECT>
					</td>
					<td>
						<INPUT type="text" onBlur="if (this.value != ''){
														eval('teste.style.wordSpacing=' + '\'' + this.value + css.vlva.value + '\'');
														css.ws.selectedIndex = 0;
														css.ws.disabled = true;
													}
													else{
														css.ws.disabled = false;
													}" id="wstxt" name="wstxt" style="width: 100%" class="campo">
					</td>
					<td>
						<SELECT name="vlws" onChange="eval('teste.style.wordSpacing=' + '\'' + css.wstxt.value + this.value + '\'');" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="px">Pixels</OPTION>
							<OPTION value="pt">Pontos</OPTION>
							<OPTION value="in">Poleg.</OPTION>
							<OPTION value="cm">Cm</OPTION>
							<OPTION value="mm">MM</OPTION>
							<OPTION value="pc">Picas</OPTION>
							<OPTION value="em">EMS</OPTION>
							<OPTION value="ex">EXS</OPTION>
						</SELECT>
				</tr>
				<tr>
					<td class="label2">Espaço entre Letras</td>
					<td>
						<SELECT onChange="eval('teste.style.letterSpacing=' + '\'' + this.value + '\'');
											if (this.value != ''){
												css.lstxt.value = '';
												css.vlls.selectedIndex = 0;
												css.lstxt.disabled = true;
												css.vlls.disabled = true;
											}
											else{
												css.lstxt.disabled = false;
												css.vlls.disabled = false;
											}" name="ls" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="Normal">Normal</OPTION>
						</SELECT>
					</td>
					<td>
						<INPUT type="text" onBlur="if (this.value != ''){
														eval('teste.style.letterSpacing=' + '\'' + this.value + css.vlls.value + '\'');
														css.ls.selectedIndex = 0;
														css.ls.disabled = true;
													}
													else{
														css.ls.disabled = false;
													}" id="lstxt" name="lstxt" style="width: 100%" class="campo">
					</td>
					<td>
						<SELECT name="vlls" onChange="eval('teste.style.letterSpacing=' + '\'' + css.lstxt.value + this.value + '\'');" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="px">Pixels</OPTION>
							<OPTION value="pt">Pontos</OPTION>
							<OPTION value="in">Poleg.</OPTION>
							<OPTION value="cm">Cm</OPTION>
							<OPTION value="mm">MM</OPTION>
							<OPTION value="pc">Picas</OPTION>
							<OPTION value="em">EMS</OPTION>
							<OPTION value="ex">EXS</OPTION>
						</SELECT>
					</td>
				</tr>
				<tr>
					<td class="label2">Identação do Texto</td>
					<td colspan="3">
						<table width="100%" cellpadding="0" cellspacing="0">
							<tr>
								<td width="50%"><INPUT type="text" onBlur="eval('teste.style.textIndent=' + '\'' + this.value + vlti.value + '\'');" name="ti" style="width: 100%" class="campo"></td>
								<td width="50%">
									<SELECT onChange="eval('teste.style.textIndent=' + '\'' + css.ti.value + this.value + '\'');" name="vlti" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</table>
					</td>
				</tr>
				<tr>
					<td class="label2">Espaços em Branco</td>
					<td colspan="3">
						<SELECT onChange="eval(this.value);" style="width: 100%" class="popup">
							<option value="teste.style.whiteSpace=''"></option>
							<OPTION value="teste.style.whiteSpace='normal'">Ignorado</OPTION>
							<OPTION value="teste.style.whiteSpace='pre'">Preservado</OPTION>
							<OPTION value="teste.style.whiteSpace='nowrap'">Sem quebra de linha</OPTION>
						</SELECT>
					</td>
				</tr>
			</TABLE>
		</div>
		<div class="conteudo" id="div5" style="visibility: hidden; position: absolute; top: 13%; left: 4%; width: 91%;">
			<TABLE width="70%" cellpadding="0">
				<tr>
				<td>
					<TABLE width="100%">
						<tr>
							<td width="50%">
								<table width="100%" cellpadding="0">
									<tr>
										<td colspan="3"  class="label3" align="center">Espaçamento</td>
									</tr>
									<tr>
										<td colspan="3" class="label2">
											<INPUT name="paddingcheckbox" type="checkbox" onClick="if (this.checked){
																										if (css.paddingtoptext.value != ''){
																											teste.style.paddingTop = css.paddingtoptext.value + css.paddingtopselect.value;
																											teste.style.paddingBottom = css.paddingtoptext.value + css.paddingtopselect.value;
																											teste.style.paddingLeft = css.paddingtoptext.value + css.paddingtopselect.value;
																											teste.style.paddingRight = css.paddingtoptext.value + css.paddingtopselect.value;
																											css.paddingbottomtext.value = css.paddingtoptext.value;
																											css.paddingrighttext.value = css.paddingtoptext.value;
																											css.paddinglefttext.value = css.paddingtoptext.value;
																											css.paddingbottomtext.disabled = true;
																											css.paddingrighttext.disabled = true;
																											css.paddinglefttext.disabled = true;
																											css.paddingbottomselect.selectedIndex = css.paddingtopselect.selectedIndex;
																											css.paddingrightselect.selectedIndex = css.paddingtopselect.selectedIndex;
																											css.paddingleftselect.selectedIndex = css.paddingtopselect.selectedIndex;
																											css.paddingbottomselect.disabled = true;
																											css.paddingrightselect.disabled = true;
																											css.paddingleftselect.disabled = true;
																										}
																									}
																									else{
																										css.paddingbottomtext.disabled = false;
																										css.paddingrighttext.disabled = false;
																										css.paddinglefttext.disabled = false;
																										css.paddingbottomselect.disabled = false;
																										css.paddingrightselect.disabled = false;
																										css.paddingleftselect.disabled = false;
																									}" checked>Igual para todos</td>
									</tr>
									<tr>
										<td width="15%" class="label2">Superior</td>
										<td width="41%"><input type="text" name="paddingtoptext" size="3" onKeyDown="if (this.value == ''){
																														paddingtopselect.selectedIndex = 1;
																														if (paddingcheckbox.checked){
																															css.paddingbottomselect.selectedIndex = css.paddingtopselect.selectedIndex;
																															css.paddingrightselect.selectedIndex = css.paddingtopselect.selectedIndex;
																															css.paddingleftselect.selectedIndex = css.paddingtopselect.selectedIndex;
																														}
																														}" onKeyUp="if (paddingcheckbox.checked){
																																		css.paddingbottomtext.value = css.paddingtoptext.value;
																																		css.paddinglefttext.value = css.paddingtoptext.value;
																																		css.paddingrighttext.value = css.paddingtoptext.value;
																																	}" onBlur="if (this.value != ''){
																																					if (paddingcheckbox.checked){
																																						teste.style.paddingTop = css.paddingtoptext.value + css.paddingtopselect.value;
																																						teste.style.paddingBottom = css.paddingtoptext.value + css.paddingtopselect.value;
																																						teste.style.paddingLeft = css.paddingtoptext.value + css.paddingtopselect.value;
																																						teste.style.paddingRight = css.paddingtoptext.value + css.paddingtopselect.value;
																																					}
																																			   }
																																			   else{
																																			   		css.paddingtopselect.selectedIndex = 0;
																																					teste.style.paddingTop = '';
																																					if (paddingcheckbox.checked){		
																																					   css.paddingbottomselect.selectedIndex = 0;
																																					   css.paddingrightselect.selectedIndex = 0;
																																					   css.paddingleftselect.selectedIndex = 0;
																																						teste.style.paddingBottom = '';
																																						teste.style.paddingLeft = '';
																																						teste.style.paddingRight = '';
																																					}		
																																			   }" style="width: 100%" class="campo">
										</td>
										<td width="33%">
											<SELECT name="paddingtopselect" onChange="	if (this.selectedIndex != 0){
																							if (paddingcheckbox.checked){
																								if (paddingtoptext.value != ''){
																									teste.style.paddingTop = css.paddingtoptext.value + css.paddingtopselect.value;
																									teste.style.paddingBottom = css.paddingtoptext.value + css.paddingtopselect.value;
																									teste.style.paddingLeft = css.paddingtoptext.value + css.paddingtopselect.value;
																									teste.style.paddingRight = css.paddingtoptext.value + css.paddingtopselect.value;
																								}
																								css.paddingbottomselect.selectedIndex = css.paddingtopselect.selectedIndex;
																								css.paddingrightselect.selectedIndex = css.paddingtopselect.selectedIndex;
																								css.paddingleftselect.selectedIndex = css.paddingtopselect.selectedIndex;
																							}
																							else {
																								if (paddingtoptext.value != ''){
																									teste.style.paddingTop = css.paddingtoptext.value + css.paddingtopselect.value;
																								}																								
																							}
																						}
																						else{
																							if (paddingcheckbox.checked){
																								css.paddingbottomselect.selectedIndex = 0;
																								css.paddingrightselect.selectedIndex = 0;
																								css.paddingleftselect.selectedIndex = 0;
																							}
																						}" style="width: 100%" class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Inferior</td>
										<td><input type="text" name="paddingbottomtext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.paddingBottom = this.value + paddingbottomselect.value;
																										 }
																										 else{
																										 	teste.style.paddingBottom = '';
																											paddingbottomselect.selectedIndex = 0;
																										 }" onKeyDown="if (paddingbottomselect.selectedIndex == 0) paddingbottomselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="paddingbottomselect" onChange="if (this.selectedIndex != 0){
																							if (paddingbottomtext.value != ''){
																						 		teste.style.paddingBottom = paddingbottomtext.value + this.value;
																							}
																						 }
																						 else {
																						 	teste.style.paddingBottom = '';
																							paddingbottomtext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Direito</td>
										<td><input type="text" name="paddingrighttext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.paddingRight = this.value + paddingrightselect.value;
																										 }
																										 else{
																										 	teste.style.paddingRight = '';
																											paddingrightselect.selectedIndex = 0;
																										 }" onKeyDown="if (paddingrightselect.selectedIndex == 0) paddingrightselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="paddingrightselect" onChange="if (this.selectedIndex != 0){
																							if (paddingrighttext.value != ''){
																						 		teste.style.paddingRight = paddingrighttext.value + this.value;
																							}	
																						 }
																						 else {
																						 	teste.style.paddingRight = '';
																							paddingrighttext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Esquerdo</td>
										<td><input type="text" name="paddinglefttext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.paddingLeft = this.value + paddingleftselect.value;
																										 }
																										 else{
																										 	teste.style.paddingLeft = '';
																											paddingleftselect.selectedIndex = 0;
																										 }" onKeyDown="if (paddingleftselect.selectedIndex == 0) paddingleftselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="paddingleftselect" onChange="if (this.selectedIndex != 0){
																							if (paddinglefttext.value != ''){
																						 		teste.style.paddingLeft = paddinglefttext.value + this.value;
																							}	
																						 }
																						 else {
																						 	teste.style.paddingLeft = '';
																							paddinglefttext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
								</table>
							</td>
							<td width="50%">
								<table width="100%" cellpadding="0">
									<tr>
										<td colspan="3"  class="label3" align="center">Margem</td>
									</tr>
									<tr>
										<td colspan="3" class="label2">
											<INPUT name="margincheckbox" type="checkbox" onClick="if (this.checked){
																										if (css.margintoptext.value != ''){
																											teste.style.marginTop = css.margintoptext.value + css.margintopselect.value;
																											teste.style.marginBottom = css.margintoptext.value + css.margintopselect.value;
																											teste.style.marginLeft = css.margintoptext.value + css.margintopselect.value;
																											teste.style.marginRight = css.margintoptext.value + css.margintopselect.value;
																											css.marginbottomtext.value = css.margintoptext.value;
																											css.marginrighttext.value = css.margintoptext.value;
																											css.marginlefttext.value = css.margintoptext.value;
																											css.marginbottomtext.disabled = true;
																											css.marginrighttext.disabled = true;
																											css.marginlefttext.disabled = true;
																											css.marginbottomselect.selectedIndex = css.margintopselect.selectedIndex;
																											css.marginrightselect.selectedIndex = css.margintopselect.selectedIndex;
																											css.marginleftselect.selectedIndex = css.margintopselect.selectedIndex;
																											css.marginbottomselect.disabled = true;
																											css.marginrightselect.disabled = true;
																											css.marginleftselect.disabled = true;
																										}
																									}
																									else{
																										css.marginbottomtext.disabled = false;
																										css.marginrighttext.disabled = false;
																										css.marginlefttext.disabled = false;
																										css.marginbottomselect.disabled = false;
																										css.marginrightselect.disabled = false;
																										css.marginleftselect.disabled = false;
																									}" checked>Igual para todos</td>
						</tr>
									<tr>
										<td width="15%" class="label2">Superior</td>
										<td width="41%"><input type="text" name="margintoptext" size="3" onKeyDown="if (this.value == ''){
																														margintopselect.selectedIndex = 1;
																														if (margincheckbox.checked){
																															css.marginbottomselect.selectedIndex = css.margintopselect.selectedIndex;
																															css.marginrightselect.selectedIndex = css.margintopselect.selectedIndex;
																															css.marginleftselect.selectedIndex = css.margintopselect.selectedIndex;
																														}
																														}" onKeyUp="if (margincheckbox.checked){
																																		css.marginbottomtext.value = css.margintoptext.value;
																																		css.marginlefttext.value = css.margintoptext.value;
																																		css.marginrighttext.value = css.margintoptext.value;
																																	}" onBlur="if (this.value != ''){
																																					if (margincheckbox.checked){
																																						teste.style.marginTop = css.margintoptext.value + css.margintopselect.value;
																																						teste.style.marginBottom = css.margintoptext.value + css.margintopselect.value;
																																						teste.style.marginLeft = css.margintoptext.value + css.margintopselect.value;
																																						teste.style.marginRight = css.margintoptext.value + css.margintopselect.value;
																																					}
																																			   }
																																			   else{
																																			   		css.margintopselect.selectedIndex = 0;
																																					teste.style.marginTop = '';
																																					if (margincheckbox.checked){		
																																					   css.marginbottomselect.selectedIndex = 0;
																																					   css.marginrightselect.selectedIndex = 0;
																																					   css.marginleftselect.selectedIndex = 0;
																																						teste.style.marginBottom = '';
																																						teste.style.marginLeft = '';
																																						teste.style.marginRight = '';
																																					}		
																																			   }" style="width: 100%" class="campo">
										</td>
										<td width="33%">
											<SELECT name="margintopselect" onChange="	if (this.selectedIndex != 0){
																							if (margincheckbox.checked){
																								if (margintoptext.value != ''){
																									teste.style.marginTop = css.margintoptext.value + css.margintopselect.value;
																									teste.style.marginBottom = css.margintoptext.value + css.margintopselect.value;
																									teste.style.marginLeft = css.margintoptext.value + css.margintopselect.value;
																									teste.style.marginRight = css.margintoptext.value + css.margintopselect.value;
																								}
																								css.marginbottomselect.selectedIndex = css.margintopselect.selectedIndex;
																								css.marginrightselect.selectedIndex = css.margintopselect.selectedIndex;
																								css.marginleftselect.selectedIndex = css.margintopselect.selectedIndex;
																							}
																							else {
																								if (margintoptext.value != ''){
																									teste.style.marginTop = css.margintoptext.value + css.margintopselect.value;
																								}																								
																							}
																						}
																						else{
																							if (margincheckbox.checked){
																								css.marginbottomselect.selectedIndex = 0;
																								css.marginrightselect.selectedIndex = 0;
																								css.marginleftselect.selectedIndex = 0;
																							}
																						}" style="width: 100%" class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Inferior</td>
										<td><input type="text" name="marginbottomtext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.marginBottom = this.value + marginbottomselect.value;
																										 }
																										 else{
																										 	teste.style.marginBottom = '';
																											marginbottomselect.selectedIndex = 0;
																										 }" onKeyDown="if (marginbottomselect.selectedIndex == 0) marginbottomselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="marginbottomselect" onChange="if (this.selectedIndex != 0){
																							if (marginbottomtext.value != ''){
																						 		teste.style.marginBottom = marginbottomtext.value + this.value;
																							}
																						 }
																						 else {
																						 	teste.style.marginBottom = '';
																							marginbottomtext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Direito</td>
										<td><input type="text" name="marginrighttext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.marginRight = this.value + marginrightselect.value;
																										 }
																										 else{
																										 	teste.style.marginRight = '';
																											marginrightselect.selectedIndex = 0;
																										 }" onKeyDown="if (marginrightselect.selectedIndex == 0) marginrightselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="marginrightselect" onChange="if (this.selectedIndex != 0){
																							if (marginrighttext.value != ''){
																						 		teste.style.marginRight = marginrighttext.value + this.value;
																							}	
																						 }
																						 else {
																						 	teste.style.marginRight = '';
																							marginrighttext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
									<tr>
										<td class="label2">Esquerdo</td>
										<td><input type="text" name="marginlefttext" size="3" onBlur="if (this.value != ''){
																										 	teste.style.marginLeft = this.value + marginleftselect.value;
																										 }
																										 else{
																										 	teste.style.marginLeft = '';
																											marginleftselect.selectedIndex = 0;
																										 }" onKeyDown="if (marginleftselect.selectedIndex == 0) marginleftselect.selectedIndex = 1;" style="width: 100%" class="campo" disabled>
										</td>
										<td>
											<SELECT name="marginleftselect" onChange="if (this.selectedIndex != 0){
																							if (marginlefttext.value != ''){
																						 		teste.style.marginLeft = marginlefttext.value + this.value;
																							}	
																						 }
																						 else {
																						 	teste.style.marginLeft = '';
																							marginlefttext.value = '';
																						 }"style="width: 100%" disabled class="popup">
												<OPTION value=""></OPTION>
												<OPTION value="px">Pixels</OPTION>
												<OPTION value="pt">Pontos</OPTION>
												<OPTION value="in">Poleg.</OPTION>
												<OPTION value="cm">Cm</OPTION>
												<OPTION value="mm">MM</OPTION>
												<OPTION value="pc">Picas</OPTION>
												<OPTION value="em">EMS</OPTION>
												<OPTION value="ex">EXS</OPTION>
												<OPTION value="%">%</OPTION>
											</SELECT>
										</td>
									</tr>
								</table>
							</td>
						</tr>
					</TABLE>
					</td>
				</tr>
				<tr>
					<td width="100%">
						<table width="100%">
							<tr>
								<td width="50%">
									<table cellpadding="0" width="100%">
										<tr>
											<td colspan="3" class="label3" align="center">Cor da Barra de Rolagem</td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor da Face</td>
											<td width="42%"><input type="text" name="scrollfacecolor" onBlur="teste.style.scrollbarFaceColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrollfacecolorbutton" onClick="javascript: selecionacor('scrollfacecolor');"></td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor Destaque</td>
											<td width="42%"><input type="text" name="scrollhighlightcolor" onBlur="teste.style.scrollbarHighLightColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrollhighlightcolorbutton" onClick="javascript: selecionacor('scrollhighlightcolor');"></td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor da Sombra</td>
											<td width="42%"><input type="text" name="scrollshadowcolor" onBlur="teste.style.scrollbarShadowColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrollshadowcolorbutton" onClick="javascript: selecionacor('scrollshadowcolor');"></td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor Luz 3D</td>
											<td width="42%"><input type="text" name="scroll3dlightcolor" onBlur="teste.style.scrollbar3dLightColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scroll3dlightcolorbutton" onClick="javascript: selecionacor('scroll3dlightcolor');"></td>
										</tr>
									</table>
								<td width="50%" valign="top">
									<table cellpadding="0" width="100%">
										<tr>
											<td colspan="3" class="label3" align="center">Cor da Barra de Rolagem</td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor da Seta</td>
											<td width="42%"><input type="text" name="scrollarrowcolor" onBlur="teste.style.scrollbarArrowColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrollarrowcolorbutton" onClick="javascript: selecionacor('scrollarrowcolor');"></td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor da Trilha</td>
											<td width="42%"><input type="text" name="scrolltrackcolor" onBlur="teste.style.scrollbarTrackColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrolltrackcolorbutton" onClick="javascript: selecionacor('scrolltrackcolor');"></td>
										</tr>
										<tr>
											<td width="45%" align="right"  class="label2">Cor da Sombra Escura</td>
											<td width="42%"><input type="text" name="scrolldarkshadowcolor" onBlur="teste.style.scrollbarDarkShadowColor = this.value;" style="width: 100%;" class="campo"></td>
											<td  width="13%"><img src="imagens/cores.gif" style="cursor: pointer;" name="scrolldarkshadowcolorbutton" onClick="javascript: selecionacor('scrolldarkshadowcolor');"></td>
										</tr>
									</table>
								</td>
							</tr>
						</table>
					</td>
				</tr>
			</TABLE>
			</td>
			</tr>
			</TABLE>
		</div>
		<div id="div6" class="conteudo" style="position: absolute; top: 13%; left: 4%; width: 91%; visibility: hidden;">
			<TABLE width="70%" cellpadding="2">
				<tr>
					<td width="50%">
						<TABLE>
							<tr>
								<td class="label2">Posição</td>
								<td colspan="2">
									<SELECT onChange="teste.style.position = this.value;" name="position" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="absolute">Absoluta</OPTION>
										<OPTION value="relative">Relativa</OPTION>
										<OPTION value="static">Estática</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td width="20%" class="label2">Largura</td>
								<td width="40%"><input type="text" name="largura" size="3" onBlur="teste.style.width = this.value + larguraselect.value" style="width: 100%" class="campo" onKeyDown="if (larguraselect.selectedIndex == 0) larguraselect.selectedIndex = 1;"></td>
								<td width="40%">
									<SELECT name="larguraselect" onChange="if (this.selectedIndex != 0){
																				teste.style.width = largura.value + larguraselect.value;
																			}
																			else {
																				largura.value = '';
																				teste.style.width = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td class="label2">Altura</td>
								<td><input type="text" name="altura" size="3" onBlur="teste.style.height = this.value + alturaselect.value" style="width: 100%" class="campo" onKeyDown="if (alturaselect.selectedIndex == 0) alturaselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="alturaselect" onChange="if (this.selectedIndex != 0){
																				teste.style.height = altura.value + alturaselect.value;
																			}
																			else {
																				altura.value = '';
																				teste.style.height = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td colspan="3" class="label3" align="center">Posicionamento</td>
							</tr>
							<tr>
								<td  class="label2">Topo</td>
								<td><input type="text" name="topo" size="3" onBlur="teste.style.top = this.value + toposelect.value" style="width: 100%" class="campo" onKeyDown="if (toposelect.selectedIndex == 0) toposelect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="toposelect" onChange="if (this.selectedIndex != 0){
																				teste.style.top = topo.value + toposelect.value;
																			}
																			else {
																				topo.value = '';
																				teste.style.top = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td  class="label2">Esquerda</td>
								<td><input type="text" name="esquerda" size="3" onBlur="teste.style.left = this.value + esquerdaselect.value" style="width: 100%" class="campo" onKeyDown="if (esquerdaselect.selectedIndex == 0) esquerdaselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="esquerdaselect" onChange="if (this.selectedIndex != 0){
																				teste.style.left = esquerda.value + esquerdaselect.value;
																			}
																			else {
																				esquerda.value = '';
																				teste.style.left = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td  class="label2">Direita</td>
								<td><input type="text" name="direita" size="3" onBlur="teste.style.right = this.value + direitaselect.value" style="width: 100%" class="campo" onKeyDown="if (direitaselect.selectedIndex == 0) direitaselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="direitaselect" onChange="if (this.selectedIndex != 0){
																				teste.style.right = direita.value + direitaselect.value;
																			}
																			else {
																				direita.value = '';
																				teste.style.right = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td  class="label2">Inferior</td>
								<td><input type="text" name="inferior" size="3" onBlur="teste.style.bottom = this.value + inferiorselect.value" style="width: 100%" class="campo" onKeyDown="if (inferiorselect.selectedIndex == 0) inferiorselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="inferiorselect" onChange="if (this.selectedIndex != 0){
																				teste.style.bottom = inferior.value + inferiorselect.value;
																			}
																			else {
																				inferior.value = '';
																				teste.style.bottom = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</TABLE>
					</td>
					<td width="50%">
						<TABLE>
							<tr>
								<td class="label2">Visibilidade</td>
								<td colspan="2">
									<SELECT onChange="teste.style.visibility = this.value;" name="visibility" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="inherit">Herdar</OPTION>
										<OPTION value="visible">Visível</OPTION>
										<OPTION value="hidden">Escondido</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td class="label2">Transbordar</td>
								<td colspan="2">
									<SELECT onChange="teste.style.overflow = this.value;" name="overflow" style="width: 100%;" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="visible">Visível</OPTION>
										<OPTION value="scroll">Barra de Rolagem</OPTION>
										<OPTION value="hidden">Escondido</OPTION>
										<OPTION value="auto">Automático</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td  class="label2">Camada</td>
								<td colspan="2"><input type="text" name="largura" size="3" onBlur="teste.style.zIndex = this.value" style="width: 100%" class="campo"></td>
							</tr>
							<tr>
								<td colspan="3" class="label3" align="center">Recortar</td>
							</tr>
							<tr>
								<td class="label2" width="20%">Topo</td>
								<td width="40%"><input type="text" name="cliptopo" size="3" onBlur="teste.style.clip.top = this.value + cliptoposelect.value" style="width: 100%" class="campo" onKeyDown="if (cliptoposelect.selectedIndex == 0) cliptoposelect.selectedIndex = 1;"></td>
								<td width="40%">
									<SELECT name="cliptoposelect" onChange="if (this.selectedIndex != 0){
																				teste.style.clip.top = cliptopo.value + cliptoposelect.value;
																			}
																			else {
																				cliptopo.value = '';
																				teste.style.clip.top = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td  class="label2">Esquerda</td>
								<td><input type="text" name="clipesquerda" size="3" onBlur="teste.style.clip.left = this.value + clipesquerdaselect.value" style="width: 100%" class="campo" onKeyDown="if (clipesquerdaselect.selectedIndex == 0) clipesquerdaselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="clipesquerdaselect" onChange="if (this.selectedIndex != 0){
																				teste.style.clip.left = clipesquerda.value + clipesquerdaselect.value;
																			}
																			else {
																				clipesquerda.value = '';
																				teste.style.clip.left = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td class="label2">Direita</td>
								<td><input type="text" name="clipdireita" size="3" onBlur="teste.style.clip.right = this.value + clipdireitaselect.value" style="width: 100%" class="campo" onKeyDown="if (clipdireitaselect.selectedIndex == 0) clipdireitaselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="clipdireitaselect" onChange="if (this.selectedIndex != 0){
																				teste.style.clip.right = clipdireita.value + clipdireitaselect.value;
																			}
																			else {
																				clipdireita.value = '';
																				teste.style.clip.right = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
							<tr>
								<td class="label2">Inferior</td>
								<td><input type="text" name="clipinferior" size="3" onBlur="teste.style.clip.bottom = this.value + clipinferiorselect.value" style="width: 100%" class="campo" onKeyDown="if (clipinferiorselect.selectedIndex == 0) clipinferiorselect.selectedIndex = 1;"></td>
								<td>
									<SELECT name="clipinferiorselect" onChange="if (this.selectedIndex != 0){
																				teste.style.clip.bottom = clipinferior.value + clipinferiorselect.value;
																			}
																			else {
																				clipinferior.value = '';
																				teste.style.clip.bottom = '';
																			}" style="width: 100%" class="popup">
										<OPTION value=""></OPTION>
										<OPTION value="px">Pixels</OPTION>
										<OPTION value="pt">Pontos</OPTION>
										<OPTION value="in">Poleg.</OPTION>
										<OPTION value="cm">Cm</OPTION>
										<OPTION value="mm">MM</OPTION>
										<OPTION value="pc">Picas</OPTION>
										<OPTION value="em">EMS</OPTION>
										<OPTION value="ex">EXS</OPTION>
										<OPTION value="%">%</OPTION>
									</SELECT>
								</td>
							</tr>
						</TABLE>
					</td>
				</tr>
			</table>
		</div>		
		<div id="div7" class="conteudo" style="position: absolute; top: 13%; left: 4%; width: 91%; visibility: hidden;">
			<table cellpadding="0" width="70%">
				<tr>
					<td class="label2" style="width: 30%">Cursor</td>
					<td style="width: 70%">
						<SELECT onChange="teste.style.cursor = this.value;" style="width: 100%;" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="hand">Mão</OPTION>
							<OPTION value="crosshair">Cruz</OPTION>
							<OPTION value="text">Texto</OPTION>
							<OPTION value="wait">Aguarde</OPTION>
							<OPTION value="default">Padrão</OPTION>
							<OPTION value="help">Ajuda</OPTION>
							<OPTION value="e-resize">Redimensionamento Leste</OPTION>
							<OPTION value="ne-resize">Redimensionamento Nordeste</OPTION>
							<OPTION value="n-resize">Redimensionamento Norte</OPTION>
							<OPTION value="nw-resize">Redimensionamento Noroeste</OPTION>
							<OPTION value="w-resize">Redimensionamento Oeste</OPTION>
							<OPTION value="sw-resize">Redimensionamento Sudoeste</OPTION>
							<OPTION value="s-resize">Redimensionamento Sul</OPTION>
							<OPTION value="se-resize">Redimensionamento Sudeste</OPTION>
							<OPTION value="auto">Automático</OPTION>
						</SELECT>
					</td>
				</tr>
				<tr>
					<td class="label2" style="width: 30%">Filtros</td>
					<td>
						<SELECT id="filtro" onChange="editafiltro(this.value);" style="width: 100%" class="popup">
							<OPTION value=""></OPTION>
							<OPTION value="Alpha">Alpha</OPTION>
							<OPTION value="AlphaImageLoader">AlphaImageLoader</OPTION>
							<OPTION value="BasicImage" >BasicImage</OPTION> 
							<OPTION value="Blur">Blur</OPTION> 
							<OPTION value="Chroma">Chroma</OPTION> 
							<OPTION value="DropShadow">DropShadow</OPTION> 
							<OPTION value="Emboss">Emboss</OPTION> 
							<OPTION value="Engrave">Engrave</OPTION>
							<OPTION value="Glow">Glow</OPTION>
							<OPTION value="Gradient">Gradient</OPTION>
							<OPTION value="MotionBlur">MotionBlur</OPTION>
							<OPTION value="Pixelate">Pixelate</OPTION>
							<OPTION value="Shadow">Shadow</OPTION>
							<OPTION value="Wave">Wave</OPTION>
						</SELECT>
					</td>
				</tr>
			</table>
			<span id="filtro_alpha" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="4" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" colspan="2">Estilo</td>
						<td colspan="2">
							<SELECT class="popup" name="alpha_type" id="alpha_type" onChange="set_filter_alpha();"> 
								<OPTION value="0">Opacidade Uniforme</OPTION> 
								<OPTION value="1">Opacidade Lineare</OPTION> 
								<OPTION value="2">Opacidade Radial</OPTION> 
								<OPTION value="3">Opacidade Retangular</OPTION>
							</SELECT>
						</td>
					</tr>
					<tr>
						<td width="100%" colspan="4"><hr></td>
					</tr>
					<tr>
						<td colspan="4" class="Label3" align="center">Digite Valores de 0 a 100</td>
					</tr>
					<tr>
						<td class="Label2">Opacidade</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="opacidade" id="opacidade"></td>
						<td class="Label2">Opacidade Final</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="opacidadefinal" id="opacidadefinal"></td>
					</tr>
					<tr>
						<td class="Label2">X Inicial</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="xinicial" id="xinicial"></td>
						<td class="Label2">X Final</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="xfinal" id="xfinal"></td>
					</tr>
					<tr>
						<td class="Label2">Y Inicial</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="yinicial" id="yinicial"></td>
						<td class="Label2">Y Final</td>
						<td><input type="text" class="campo" onBlur="set_filter_alpha();" name="yfinal" id="yfinal"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_AlphaImageLoader" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="3" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="33%">Imagem</td>
						<td width="33%"><input type="text" class="campo" onBlur="set_filter_alphaimageloader();" name="imagemalfafiltro" id="imagemalfafiltro" style="width: 100%"></td>
						<td width="33%"><img onClick="arq(imagemalfafiltro.form.name + '.' + imagemalfafiltro.name);" style="cursor: pointer;" src="imagens/procurar.gif"></td>
					</tr>
					<tr>
						<td class="Label2">Método de Dimensionamento</td>
						<td colspan="2">
							<SELECT class="popup" name="alphaimageloader_type" id="alphaimageloader_type" onChange="set_filter_alphaimageloader();"> 
								<OPTION value='crop' SELECTED>Recorte</OPTION> 
								<OPTION value='image'>Dimensionar do tamanho da Imagem</OPTION>
								<OPTION value='scale'>Dimensionar a Imagem para o Tamanho</OPTION> 
							</SELECT>
						</td>
					</tr>
					<tr>
						<td width="100%" colspan="3"><hr></td>
					</tr>
				</table>
			</span>
			<span id="filtro_basicimage" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="4" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2">Rotação</td>
						<td colspan="3">
							<SELECT class="popup" name="basicimage_rotation" id="basicimage_rotation" onChange="set_filter_basicimage();" style="width: 70%;"> 
								<OPTION value="0">0 Graus</OPTION> 
								<OPTION value="1">90 Graus</OPTION> 
								<OPTION value="2">180 Graus</OPTION> 
								<OPTION value="3">270 Graus</OPTION>
							</SELECT>
						</td>
					</tr>
					<tr>
						<td class="Label2">Opacidade (0.0 a 1.0)</td>
						<td colspan="3"><input type="text" class="campo" onBlur="set_filter_basicimage();" name="basicimage_opacity" id="basicimage_opacity" style="width: 70%;"></td>
					</tr>
					<tr>
						<td width="100%" colspan="4"><hr></td>
					</tr>
					<tr>
						<td width="25%" class="label2">Espelho</td>
						<td width="25%"><input type="checkbox" name="basicimage_espelho" id="basicimage_espelho" onClick="set_filter_basicimage();"></td>
						<td width="25%" class="label2">Inverter</td>
						<td width="25%"><input type="checkbox" name="basicimage_inverter" id="basicimage_inverter" onClick="set_filter_basicimage();"></td>
					</tr>
					<tr>
						<td width="25%" class="label2">Raio X</td>
						<td width="25%"><input type="checkbox" name="basicimage_raiox" id="basicimage_raiox" onClick="set_filter_basicimage();"></td>
						<td width="25%" class="label2">Tons de Cinza</td>
						<td width="25%"><input type="checkbox" name="basicimage_cinza" id="basicimage_cinza" onClick="set_filter_basicimage();"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_blur" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="2" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="50%">Raio do Pixel</td>
						<td  width="50%">
							<input type="text" class="campo" name="blur_pixel" id="blur_pixel" onBlur="set_filter_blur();" style="width: 70%;"> 
						</td>
					</tr>
					<tr>
						<td class="Label2">Fazer Sombra</td>
						<td colspan="3"><INPUT type="checkbox" name="blur_box" id="blur_box" onclick="set_filter_blur();"></td>
					</tr>
					<tr>
						<td class="Label2">Opacidade (0.0 a 1.0)</td>
						<td colspan="3"><input type="text" class="campo" onBlur="set_filter_blur();" name="blur_shadow" id="blur_shadow" style="width: 70%;"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_croma" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="3" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="25%">Cor</td>
						<td  width="50%">
							<input type="text" class="campo" name="croma_cor" id="croma_cor" onBlur="set_filter_croma();" style="width: 100%;"> 
						</td>
						<td width="25%"><img onClick="javascript: selecionacor('croma');" style="cursor: pointer;" src="imagens/cores.gif"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_drop_shadow" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%" cellspacing="2">
					<tr>
						<td class="label3" align="center" colspan="4" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="25%">Cor</td>
						<td colspan="2"><input type="text" class="campo" name="drop_shadow_cor" id="drop_shadow_cor" onBlur="set_filter_drop_shadow();" style="width: 100%;"></td>
						<td width="25%"><img onClick="javascript: selecionacor('drop_shadow');" style="cursor: pointer;" src="imagens/cores.gif"></td>
					</tr>
					<tr>
						<td class="Label2" colspan="2">Positivo</td>
						<td colspan="2"><INPUT type="checkbox" name="drop_shadow_box" id="drop_shadow_box" onclick="set_filter_drop_shadow();" checked></td>
					</tr>
					<tr>
						<td class="Label2">X</td>
						<td  width="20%"><input type="text" class="campo" onBlur="set_filter_drop_shadow();" name="drop_shadow_x" id="drop_shadow_x" width="100%"></td>
						<td  width="20%"><input type="text" class="campo" onBlur="set_filter_drop_shadow();" name="drop_shadow_y" id="drop_shadow_y" width="100%"></td>
						<td class="Label3">Y</td>
					</tr>
				</table>
			</span>
			<span id="filtro_glow" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="3" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="25%">Cor</td>
						<td  width="50%"><input type="text" class="campo" name="glow_cor" id="glow_cor" onBlur="set_filter_glow();" style="width: 100%;"></td>
						<td width="25%"><img onClick="javascript: selecionacor('glow');" style="cursor: pointer;" src="imagens/cores.gif"></td>
					</tr>
					<tr>
						<td class="Label2">Quantidade</td>
						<td><input type="text" class="campo" onBlur="set_filter_glow();" name="qtglow" id="qtglow" style="width: 100%"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_gradient" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="3" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td width="25%" class="label2">Vertical</td>
						<td width="25%"><input type="checkbox" name="gradient_type1" id="gradient_type1" onClick="if (gradient_type2.checked) gradient_type2.checked = false; set_filter_gradient();" checked></td>
						<td width="25%" class="label2">Horizontal</td>
						<td width="25%"><input type="checkbox" name="gradient_type2" id="gradient_type2" onClick="if (gradient_type1.checked) gradient_type1.checked = false; set_filter_gradient();"></td>
					</tr>
					<tr>
						<td class="Label2" width="25%">Cor</td>
						<td colspan="2" width="50%"><input type="text" class="campo" name="gradient_start_color" id="gradient_start_color" onBlur="set_filter_gradient();" style="width: 100%;"></td>
						<td width="25%"><img onClick="javascript: selecionacor('gradient1');" style="cursor: pointer;" src="imagens/cores.gif"></td>
					</tr>
					<tr>
						<td class="Label2" width="25%">Cor</td>
						<td colspan="2" width="50%"><input type="text" class="campo" name="gradient_end_color" id="gradient_end_color" onBlur="set_filter_gradient();" style="width: 100%;"></td>
						<td width="25%"><img onClick="javascript: selecionacor('gradient2');" style="cursor: pointer;" src="imagens/cores.gif"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_motionblur" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="2" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="50%">Direção (0 - 360<SUP>o</SUP>)</td>
						<td  width="50%">
							<input type="text" class="campo" name="mblur_direction" id="mblur_direction" onBlur="set_filter_motionblur();" style="width: 70%;"> 
						</td>
					</tr>
					<tr>
						<td class="Label2">Quantidade</td>
						<td colspan="3"><input type="text" class="campo" onBlur="set_filter_motionblur();" name="mblur_qt" id="mblur_qt" style="width: 70%;"></td>
					</tr>
				</table>
			</span>
			<span id="filtro_pixel" class="conteudo" style="position: absolute; top: 150%; left: 10%; width: 91%; visibility: hidden;">
				<table width="70%">
					<tr>
						<td class="label3" align="center" colspan="2" style="FILTER: progid:DXImageTransform.Microsoft.Gradient(gradientType=1,startColorStr=#AAFFFF,endColorStr=#FFFFFF);">Atributos</td>
					</tr>
					<tr>
						<td class="Label2" width="50%">Quadrado Máximo (2 - 50)</td>
						<td  width="50%">
							<input type="text" class="campo" name="pixmax" id="pixmax" onBlur="set_filter_pixel();" style="width: 70%;"> 
						</td>
					</tr>
				</table>
			</span>
		</div>
		<div id="teste" name="teste" style="width: 150px; height: 150px; right: 25px; top: 50px; position: absolute">Área de Testes<br>Área de Testes<br>Área de Testes<br>Área de Testes<br></div>
	</form>
	</BODY>
	<SCRIPT language="JavaScript" type="text/javascript">

		function set_filter_pixel(){
			var filtro = "FILTER: progid:DXImageTransform.Microsoft.Pixelate(maxsquare=";
			if (css.pixmax.value == "") css.pixmax.value = "10"; 
			teste.style.filter = filtro + css.pixmax.value + ")";
		}

		function set_filter_motionblur(){
			var filtro = "progid:DXImageTransform.Microsoft.MotionBlur(direction="
			if (css.mblur_direction.value == "") css.mblur_direction.value = "60";
			filtro += css.mblur_direction.value;
			if (css.mblur_qt.value == "") css.mblur_qt.value = "5";
			filtro += ",strength=" + css.mblur_qt.value + ")";
			teste.style.filter = filtro;
		}
		function set_filter_gradient(){
			var filtro = "progid:DXImageTransform.Microsoft.Gradient(gradientType=";
			if (css.gradient_type1.checked) filtro += "0";
			else filtro += "1";
			if (css.gradient_start_color.value == "") css.gradient_start_color.value = "#00FF00";
			filtro += ",startColorStr=" + css.gradient_start_color.value;
			if (css.gradient_end_color.value == "") css.gradient_end_color.value = "#FF0000";
			filtro += ",endColorStr=" + css.gradient_end_color.value + ")";
			teste.style.filter = filtro;
		}
		function set_filter_glow(){
			filtro = "progid:DXImageTransform.Microsoft.Glow(color=";
			if (css.glow_cor.value != "") filtro += css.glow_cor.value;
			else {
				filtro += "#FF0000";
				css.glow_cor.value = "#FF0000";
			}
			if (css.qtglow.value != "") filtro += ",strength=" + css.qtglow.value;
			else {
				css.qtglow.value = "5";
				filtro += ",strength=5";
			}
			filtro += ")";
			teste.style.filter = filtro;
		}
		
		function set_filter_drop_shadow(){
			var filtro = "progid:DXImageTransform.Microsoft.dropShadow(Color=";
			if (css.drop_shadow_cor.value != "") filtro += css.drop_shadow_cor.value;
			else {
				filtro += "#999999";
				css.drop_shadow_cor.value = "#999999";
			}
			if (css.drop_shadow_x.value != "") filtro += ",offX=" + css.drop_shadow_x.value;
			else {
				filtro += ",offX=5";
				css.drop_shadow_x.value = "5";
			}
			if (css.drop_shadow_y.value != "") filtro += ",offY=" + css.drop_shadow_y.value;
			else {
				filtro += ",offY=5";
				css.drop_shadow_y.value = "5";
			}
			if (css.drop_shadow_box.checked) filtro += ",positive=true";
			else filtro += ",positive=false";
			
			teste.style.filter = filtro + ")";
		}
		function set_filter_croma(){
			teste.style.filter = "progid:DXImageTransform.Microsoft.Chroma(Color=" + css.croma_cor.value + ")";
		}
			
		function set_filter_blur(){
			var filtro = "progid:DXImageTransform.Microsoft.Blur( PixelRadius=";
			if (css.blur_pixel.value != ""){
				filtro += css.blur_pixel.value + ",MakeShadow=";
			}
			else{
				css.blur_pixel.value = "5";
				filtro += "5" + ",MakeShadow=";
			}
			if (css.blur_box.checked){
				filtro += "true,ShadowOpacity=";
				if (css.blur_shadow.value != "") filtro += css.blur_shadow.value; 
				else {
					filtro += "1.00";
					css.blur_shadow.value = "1.00";
				}
			}
			else filtro += "false";
			teste.style.filter = filtro + ")"
		}
		function set_filter_basicimage(){
			var filtro = "progid:DXImageTransform.Microsoft.BasicImage(Rotation=";
			if (css.basicimage_rotation.value == "") css.basicimage_rotation.value = "0";
			
			filtro += css.basicimage_rotation.value;
			
			if (css.basicimage_opacity.value != ""){
				filtro += ",Opacity=" + css.basicimage_opacity.value;			
			}
			if (css.basicimage_espelho.checked){
				filtro += ",Mirror=1";
			}
			else filtro += ",Mirror=0";
			if (css.basicimage_inverter.checked){
				filtro += ",Invert=1";
			}
			else filtro += ",Invert=0";
			if (css.basicimage_raiox.checked){
				filtro += ",XRay=1";
			}
			else filtro += ",XRay=0";
			if (css.basicimage_cinza.checked){
				filtro += ",Grayscale=1";
			}
			else filtro += ",Grayscale=0";
			filtro += ")";
			teste.style.filter = filtro;
		}
		function set_filter_alphaimageloader(){
			var filtro;
			if (css.imagemalfafiltro.value != ""){
				filtro = "progid:DXImageTransform.Microsoft.AlphaImageLoader(src=";
				filtro += css.imagemalfafiltro.value;
				filtro += ",sizingmethod=" + css.alphaimageloader_type.value + ")";
				teste.style.filter = filtro;
			}	
		}
		function editafiltro(valor){
			if (div_filtro != ""){
				eval(div_filtro + ".style.visibility = 'hidden'");
			}
			switch(valor){ 
				case ("Pixelate"):
					filtro_pixel.style.visibility = "visible";
					div_filtro = "filtro_pixel";
					set_filter_pixel();
					break;
				case ("MotionBlur"):
					filtro_motionblur.style.visibility = "visible";
					div_filtro = "filtro_motionblur";
					set_filter_motionblur();
					break;
				case ("Alpha"):
					filtro_alpha.style.visibility = "visible";
					div_filtro = "filtro_alpha";
					set_filter_alpha();
					break;
				case (""):
					teste.style.filter = "";
					break;
				case ("Glow"):
					filtro_glow.style.visibility = "visible";
					div_filtro = "filtro_glow";
					set_filter_glow();
					break;
				case ("Engrave"):
					teste.style.filter = "progid:DXImageTransform.Microsoft.Engrave()";
					break;
				case ("Emboss"):
					teste.style.filter = "progid:DXImageTransform.Microsoft.Emboss()";
					break;
				case ("DropShadow"):
					filtro_drop_shadow.style.visibility = "visible";
					div_filtro = "filtro_drop_shadow";
					set_filter_drop_shadow();
					break;
				case ("Gradient"):
					filtro_gradient.style.visibility = "visible";
					div_filtro = "filtro_gradient";
					set_filter_gradient();
					break;
				case ("AlphaImageLoader"):
					filtro_AlphaImageLoader.style.visibility = "visible";
					div_filtro = "filtro_AlphaImageLoader";
					set_filter_alphaimageloader
					break;
				case ("BasicImage"):
					filtro_basicimage.style.visibility = "visible";
					div_filtro = "filtro_basicimage";
					set_filter_basicimage();
					break;
				case ("Blur"):
					filtro_blur.style.visibility = "visible";
					div_filtro = "filtro_blur";
					set_filter_blur();
					break;
				case ("Chroma"):
					filtro_croma.style.visibility = "visible";
					div_filtro = "filtro_croma";
					set_filter_croma();
					break;
			}
		}
		function set_filter_alpha(){
			filtro = "Alpha(style=" + css.alpha_type.value + ",";
			if (css.opacidade.value == ""){
				filtro += "opacity=50";
				css.opacidade.value = "50";
			}
			else{
				filtro += "opacity=" + css.opacidade.value;
				if (css.alpha_type.value == 1){
					if (css.opacidadefinal.value != ""){
						filtro += ",finishOpacity=" + css.opacidadefinal.value + ",";					
					}
					if (css.xinicial.value != ""){
						filtro += ",startX=" + css.xinicial.value;
					}
					if (css.xfinal.value != ""){
						filtro += ",finishX=" + css.xfinal.value;
					}
					if (css.yinicial.value != ""){
						filtro += ",startY=" + css.yinicial.value;
					}
					if (css.yfinal.value != ""){
						filtro += ",finishY=" + css.yfinal.value;
					}
				}
			}
			filtro += ")";
			teste.style.filter = filtro;
		}
		
		function selecionacor(what){
			var win = window.open('selecionacores.html?what=' + what,'newWin','scrollbars=no,status=no,menubar=no, width=460, height=320');
		}
		function arq(oque){
			var w = window.open('files.asp?dir=<%=local%>&oque=' + oque,'newWin');
		}
		function bgposition1(valor){
			var ss = teste.style.backgroundPosition.split(" ");
			if (valor != ''){
				if (teste.style.backgroundPosition != "")
					teste.style.backgroundPosition = valor + " " + ss[1];
				else
					teste.style.backgroundPosition = valor + " top";
			}
			else teste.style.backgroundPosition = "left " + ss[1];
		}
		function bgposition2(valor){
			var ss = teste.style.backgroundPosition.split(" ");
			if (valor != ''){
				if (teste.style.backgroundPosition != "")
					teste.style.backgroundPosition = ss[0] + " " + valor;
				else
					teste.style.backgroundPosition = valor;
			}
			else teste.style.backgroundPosition = ss[0] + " top";
		}
	</SCRIPT>
</HTML>
