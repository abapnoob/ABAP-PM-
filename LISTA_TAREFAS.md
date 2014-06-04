REPORT lista_tarefas.

TYPE-POOLS: slis.

*-----------------------------------------------------------------------
* Tabelas Transparentes
*-----------------------------------------------------------------------
TABLES: ztbpm_eqp_depara. "De / Para Pontos de Medição

* Tabela de cabeçalho
TYPES: BEGIN OF y_cab,
      plnnr(8)         TYPE c,    "Num. roteiro
      equnr(25)        TYPE c,    "Equipamento
      tplnr(40)        TYPE c,    "Local de Instalação
      datuv(10)        TYPE c,    "data fixada
      plnal(2)         TYPE c,    "n.grupos
      ktext(40)        TYPE c,    "texto breve
      werk(4)          TYPE c,    "Centro
      arbpl(8)         TYPE c,    "CT
      werks(4)         TYPE c,    "centro do CT
      verwe(3)         TYPE c,    "Utilização
      vagrp(3)         TYPE c,    "gr.pl.trabalho
      statu(1)         TYPE c,    "Status
      anlzu(1)         TYPE c,    "estado inst.
      strat(6)         TYPE c,    "Estratégia
      istru(18)        TYPE c,    "conj.
      slwbez(3)        TYPE c,    "comb.pto.cont
      profidnetz(7)    TYPE c,                  "Perfil
  END OF y_cab,

* Arquivo de Operações
  BEGIN OF y_ope,
       plnnr(8)         TYPE c, "Num. roteiro
       plnal(02)        TYPE c, "Numerador de grupos
       vornr(4)         TYPE c, "op.
       uvorn(4)         TYPE c, "Suboperação
       arbpl(8)         TYPE c, "CT
       steus(4)         TYPE c, "Chave de controle
       ltxa1(40)        TYPE c, "descrição op.
       arbei(7)         TYPE c, "trabalho
       arbeh(3)         TYPE c, "unidade
       anzzl(3)         TYPE c, "n.cap.nec.
       dauno(6)         TYPE c, "duração
       daune(3)         TYPE c, "Unidade
       indet(1)         TYPE c, "ch.cálculo
       prznt(3)         TYPE c, "%trabalho
       vertn(8)         TYPE c, "dist.nec.cap.
       aufkt(3)         TYPE c, "fator exec.
       larnt(6)         TYPE c, "Tipo de atividade
       ktsch(7)         TYPE c, "ch.modelo
       istru(18)        TYPE c, "conj.
       loanz(3)         TYPE c, "n.fl.tmp.
       logrp(18)        TYPE c, "gr.salarial
       qualf(2)         TYPE c, "qualificação
       kzlgf(1)         TYPE c, "proc.terc.lote fixo
       bmvrg(13)        TYPE c, "qdade pedida
       bmeih(3)         TYPE c, "unid.pedido
       preis(11)        TYPE c, "preço líquido
       peinh(5)         TYPE c, "unid.preço
       plifz(3)         TYPE c, "prazo prev. Fornc.
       sakto(10)        TYPE c, "classe custo
       matkl(9)         TYPE c, "gr.mercadorias
       ekgrp(3)         TYPE c, "gr.compras
       lifnr(10)        TYPE c, "fornecedor
       ekorg(4)         TYPE c, "org. compras
       sortl(10)        TYPE c, "cr.ordenação
       srvpos(12)       TYPE c, "Número do Serviço
       ktext1(40)       TYPE c, "Texto Breve
       menge(18)        TYPE c, "Quantidade
       meins(3)         TYPE c, "Preço bruto
       tbtwr(15)        TYPE c, "Sem Limite
       slwid(7)         TYPE c, "Campo de usuario
       usr00(20)        TYPE c, "Número Ponto de Medição
    END OF y_ope,

*Pacotes
    BEGIN OF y_pac,
        plnnr(8)     TYPE c, "Grupo listas tarefas
        plnal(02)    TYPE c, "Numerador de grupos
        vornr(4)     TYPE c, "op.
        uvorn(4)     TYPE c,"Suboperação
        paket(1)     TYPE c, "Pacote
    END OF y_pac,

* Componente
    BEGIN OF y_comp,
        plnnr(8)     TYPE c, "Grupo listas tarefas
        plnal(2)     TYPE c, "Numerador de grupos
        vornr(4)     TYPE c, "Operação
        uvorn(4)     TYPE c, "Suboperação
        idnrk(18)    TYPE c, "MAterial
        menge(13)    TYPE c, "Quantidade
        meins(3)     TYPE c, "Unidade de Medida
        rgekz(1)     TYPE c, "Baixa Explosão
        disp(1)      TYPE c, "Relevancia MRP
    END OF y_comp,

* MAP
    BEGIN OF y_map,
        plnnr(8)     TYPE c, "n. roteiro
        plnal(2)     TYPE c, "Numerador de grupos.
        vornr(4)     TYPE c, "Operação
        uvorn(4)     TYPE c, "Suboperação
        psnfh(4)     TYPE c, " n.item MAP
        matnr(18)    TYPE c, "Material
        werks(4)     TYPE c, "centro MAP
        mgvgw(9)     TYPE c, "qdade MAP
        equnr(18)    TYPE c, "equipamento
        steuf(4)     TYPE c, "ch.controle
     END OF y_map,

*Caracteristicas
     BEGIN OF y_car,
        plnnr(8)       TYPE c, "Num. roteiro
        plnal(2)       TYPE c, "Numerador de grupos
        vornr(4)       TYPE c, "op.
        uvorn(4)       TYPE c, "Suboperação
        merknr(4)      TYPE c, "Número da Característica de Controle.
        verwmerkm(8)   TYPE c, "Característica Mestre de Controle
        qpmk_zaehl(4)  TYPE c, "Centro
        mkversion(6)   TYPE c, "versão
        kurztext(40)   TYPE c, "Texto breve da caracteristicas
        pmethode(8)    TYPE c, "Método de controle
        qmtb_werks(4)  TYPE c, "Centro para método de controle
        pmtversion(6)  TYPE c, "Versão do método
        stichprver(8)  TYPE c, "Processo de amostra
        probenr(3)     TYPE c, "Amostra parcial
        pruefquali(5)  TYPE c, "Qualificação inspetor
        eeantverf(2)   TYPE c, "Cálculo percentual
        merkgew(10)    TYPE c, "Ponderação de características
        charact_id1(40) TYPE c, "ID interno
        qergdath(10)   TYPE c, "Origem dos dados
        dummy10(10)    TYPE c, " Campo info 1
        dummy20(20)    TYPE c, " Campo info 2
        dummy40(40)    TYPE c, " Campo info 3
        stellen(2)     TYPE c, "Número de Casas Decimais
        masseinhsw(6)  TYPE c, "Unidade Medida
        sollwert(16)   TYPE c, "Valor Teórico
        toleranzun(16) TYPE c, "Limite Inferior
        toleranzob(16) TYPE c, "Valor Limite Superior
        plausiunte(16) TYPE c, "Limite Inf. Plausivel
        plausioben(16) TYPE c, "Limite Superior Plausível
        formel1(60)    TYPE c, "Formula 1
        formel2(60)    TYPE c, "Formula 2
        katalgart2(1)  TYPE c, "Tipo Catalogo
        auswmenge2(8)  TYPE c, "Grupo de codes
        auswmgwrk2(4)  TYPE c, "Centro catalogo
        codegrqual(8)  TYPE c, "Grupo de Code Defeito Geral
        codequal(4)    TYPE c, "Code defeito geral
        codegr9o(8)    TYPE c, "Grupo de Code Toler. Sup.
        code9o(4)      TYPE c, "Code Toler. Sup
        codegr9u(8)    TYPE c, "Grupo Code Tol. Inf.
        code9u(4)      TYPE c, "Code Toler. Inf.
     END OF y_car,

* textos longos
     BEGIN OF y_text,
        plnnr(8)       TYPE c, "Grupo lista tarefa
        plnal(2)       TYPE c, "Numerador de grupos
        werks(4)       TYPE c, "Centro
        vornr(4)       TYPE c, "Operação
        uvorn(4)       TYPE c, "suboperação
*        ltxa1(40)      TYPE c, "Texto longo
        caminho(128)   TYPE c, "caminho
     END OF y_text,

     BEGIN OF y_log,
       plnnr(8)        TYPE c, "Grupo lista tarefa
       messg(255)      TYPE c, " Mensagem
     END OF y_log,

     BEGIN OF y_equip,
       equnr_de TYPE ztbpm_eqp_depara-equnr_de,
       equnr_para TYPE ztbpm_eqp_depara-equnr_para,
     END OF y_equip,

  BEGIN OF y_empresa,
  bukrs TYPE t001-bukrs,
  END OF y_empresa,

  BEGIN OF y_cab_aux,
   plnnr_ref TYPE plpo-plnnr,
   plnnr TYPE plpo-plnnr,
   plnty TYPE c,
   plnal_ref TYPE plko-plnal,
   plnal TYPE plko-plnal,
   profidnetz(7)  TYPE c,
   werks  TYPE werks_d,
  END OF y_cab_aux.


TYPES: BEGIN OF y_plpo,
       plnty    TYPE plpo-plnty,
       plnnr    TYPE plpo-plnnr,
       plnkn    TYPE plpo-plnkn,
       zaehl    TYPE plpo-zaehl,
       sumnr    TYPE plpo-sumnr,
       vornr    TYPE plpo-vornr,
       END OF y_plpo.

TYPES: BEGIN OF y_aux,
  plnnr     TYPE plpo-plnnr,
  plnty     TYPE plpo-plnty,
  plnnr_new TYPE plpo-plnnr,
  END OF y_aux.

***************************************************************************
*  Tabela Interna                                                         *
***************************************************************************
DATA: t_cab               TYPE TABLE OF y_cab,
      t_ope               TYPE TABLE OF y_ope,
      t_pac               TYPE TABLE OF y_pac,
      t_comp              TYPE TABLE OF y_comp,
      t_map               TYPE TABLE OF y_map,
      t_car               TYPE TABLE OF y_car,
      t_text              TYPE TABLE OF y_text,
      t_log               TYPE TABLE OF y_log,
      t_equip             TYPE TABLE OF y_equip,
      t_aux               TYPE TABLE OF y_aux.

DATA: t_arq               TYPE TABLE OF string,
      t_cab_arq           TYPE TABLE OF string,
      t_ope_arq           TYPE TABLE OF string,
      t_pac_arq           TYPE TABLE OF string,
      t_comp_arq          TYPE TABLE OF string,
      t_map_arq           TYPE TABLE OF string,
      t_car_arq           TYPE TABLE OF string,
      t_text_arq          TYPE TABLE OF string,
      t_cab_aux           TYPE TABLE OF y_cab_aux,
      t_empresa           TYPE TABLE OF y_empresa,
      t_lines             TYPE TABLE OF tline,
      t_plpo              TYPE TABLE OF y_plpo,
      t_sub               TYPE TABLE OF y_plpo.

* tabelas da bapi
DATA: t_ope_bapi          TYPE TABLE OF eam_s_tl_opr,
      t_comp_bapi         TYPE TABLE OF eam_s_tl_plmz_up,
      t_pac_bapi          TYPE TABLE OF eam_s_tl_mpack,
      t_map_bapi          TYPE TABLE OF eam_s_tl_prt,
      t_serv_bapi         TYPE TABLE OF eam_s_tl_spack,
      t_text_bapi         TYPE TABLE OF eam_s_text,
      t_text_l_bapi       TYPE TABLE OF eam_s_text_lines,
      t_return_cre        TYPE TABLE OF bapiret2,
      t_return_mod        TYPE TABLE OF bapiret2.

DATA: t_messtab           LIKE bdcmsgcoll OCCURS 0 WITH HEADER LINE,
      t_bdc               LIKE bdcdata OCCURS 0 WITH HEADER LINE,
* TRATAMENTO DO ALV
      t_layout            TYPE slis_layout_alv,
      t_fieldcat          TYPE slis_t_fieldcat_alv WITH HEADER LINE.
***************************************************************************
*  Work Areas                                                             *
***************************************************************************
DATA: w_cab               TYPE y_cab,
      w_ope               TYPE y_ope,
      w_ope_aux           TYPE y_ope,
      w_pac               TYPE y_pac,
      w_pac_aux           TYPE y_pac,
      w_comp              TYPE y_comp,
      w_comp_aux          TYPE y_comp,
      w_map               TYPE y_map,
      w_map_aux           TYPE y_map,
      w_car               TYPE y_car,
      w_car_aux           TYPE y_car,
      w_text              TYPE y_text,
      w_text_aux          TYPE y_text,
      w_cab_aux           TYPE y_cab_aux,
      w_log               TYPE y_log,
      w_equip             TYPE y_equip,
      w_empresa           TYPE y_empresa,
      w_fieldcat          TYPE slis_fieldcat_alv,
      w_layout            TYPE slis_layout_alv,
      w_plpo              TYPE y_plpo,
      w_header            TYPE thead,
      w_lines             TYPE tline,
      w_sub               TYPE y_plpo.

* work areas da bapi
DATA: w_ope_bapi    TYPE eam_s_tl_opr,
      w_comp_bapi   TYPE eam_s_tl_plmz_up,
      w_pac_bapi    TYPE eam_s_tl_mpack,
      w_map_bapi    TYPE eam_s_tl_prt,
      w_serv_bapi   TYPE eam_s_tl_spack,
      w_l_bapi      TYPE eam_s_text_lines,
      w_text_bapi   TYPE eam_s_text,
      w_return_cre  TYPE bapiret2,
      w_return_mod  TYPE bapiret2,
      w_cab_bapi    TYPE eam_s_hdr_ins, " HEADER da bapi
      w_aux         TYPE y_aux.

DATA: w_arq  TYPE string.
***************************************************************************
*  Constantes                                                             *
***************************************************************************
CONSTANTS: c_i          TYPE c VALUE 'I',
           c_x          TYPE c VALUE 'X',
           c_csv(10)    TYPE c VALUE '*.csv',
           c_e          TYPE c VALUE 'E',
           c_m          TYPE c VALUE 'M',
           c_t          TYPE c VALUE 'T',
           c_a          TYPE c VALUE 'A',
           c_%          TYPE c VALUE '%',
           c_object(10) TYPE c VALUE 'M_MATE_BUK',
           c_pm03(4)    TYPE c VALUE 'PM03',
           c_bukrs(5)   TYPE c VALUE 'BUKRS',
           c_actvt(5)   TYPE c VALUE 'ACTVT',
           c_02(2)      TYPE c VALUE '02',
           c_sep(1)     TYPE c VALUE ';',
           c_ia01(4)    TYPE c VALUE 'IA01',
           c_ia02(4)    TYPE c VALUE 'IA02',
           c_pt         TYPE c VALUE 'P',
           c_ia06(4)    TYPE c VALUE 'IA06',
           c_ia12(4)    TYPE c VALUE 'IA12',
           c_ia11(4)    TYPE c VALUE 'IA11',
           c_ia05(4)    TYPE c VALUE 'IA05',
           c_s          TYPE c VALUE 'S',
           c_messg(5)   TYPE c VALUE 'MESSG',
           c_plnnr(5)   TYPE c VALUE 'PLNNR',
           c_120(3)     TYPE c VALUE '120',
           c_programm   TYPE ztbbc_parametros-programm VALUE 'ZGLCPM0015_LISTA_TAREFAS',
           c_pm01(5)    TYPE c VALUE 'PM01',
           c_10(2)      TYPE c VALUE '10'.

DATA:      v_caminho    TYPE string,
           v_li         TYPE string, " Linha do arquivo
           v_plnty      TYPE c,
           v_modo       TYPE c VALUE 'N',
           v_mesg       TYPE message VALUE  IS INITIAL,
           v_mapm       TYPE c.

DATA:     v_plnnr TYPE plpo-plnnr,
          v_plnal TYPE plko-plnal,
          v_flag  TYPE c.
***************************************************************************
*  Tela de Seleção                                                        *
***************************************************************************
SELECTION-SCREEN BEGIN OF BLOCK b1 WITH FRAME TITLE text-t01.
PARAMETERS: p_filecb LIKE rlgrap-filename  OBLIGATORY. " Cabeçalho
PARAMETERS: p_fileop LIKE rlgrap-filename  OBLIGATORY. " Operações
PARAMETERS: p_filept LIKE rlgrap-filename            . " Pacotes
PARAMETERS: p_filecp LIKE rlgrap-filename            . " Componentes
PARAMETERS: p_filemp LIKE rlgrap-filename            . " Maps
PARAMETERS: p_filecr LIKE rlgrap-filename            . " Características
PARAMETERS: p_filetl LIKE rlgrap-filename            . " textos longos

SELECTION-SCREEN SKIP.
SELECTION-SCREEN BEGIN OF BLOCK b2 WITH FRAME TITLE text-t02.
PARAMETERS: p_locl RADIOBUTTON GROUP rad1 USER-COMMAND rd01 DEFAULT 'X',
            p_serv RADIOBUTTON GROUP rad1.
PARAMETERS  p_test AS CHECKBOX.
SELECTION-SCREEN END OF BLOCK b2.
SELECTION-SCREEN END OF BLOCK b1.
***************************************************************************
*  AT-Selection SCREEN                                                    *
***************************************************************************
AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filecb.
* localizar arquivo de cabeçalho
  PERFORM zf_buscar_arquivo USING p_filecb.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_fileop.
* localizar arquivo de operações
  PERFORM zf_buscar_arquivo USING p_fileop.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filept.
* localizar arquivo de pacotes
  PERFORM zf_buscar_arquivo USING p_filept.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filecp.
* localizar arquivo de componentes
  PERFORM zf_buscar_arquivo USING p_filecp.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filemp.
* localizar arquivo de maps
  PERFORM zf_buscar_arquivo USING p_filemp.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filecr.
* localizar arquivo de Caracteristicas
  PERFORM zf_buscar_arquivo USING p_filecr.

AT SELECTION-SCREEN ON VALUE-REQUEST FOR p_filetl.
* localizar arquivo de texto longos
  PERFORM zf_buscar_arquivo USING p_filetl.

***************************************************************************
*  AT-Selection SCREEN                                                    *
***************************************************************************
START-OF-SELECTION.

  PERFORM zf_valida_perfil_acesso.
* Limpar tabelas e variáveis
  PERFORM zf_limpar_tab_var.

* Verificar se opção para busca de arquivo é para Ambiente
* Local(P_locl) ou UNIX(P_serv) e carrega t_arq antes do split.
  PERFORM zf_verifica_win_unix.

  IF  NOT  p_filecb IS INITIAL AND NOT p_fileop IS INITIAL AND p_filept IS INITIAL
     AND p_filecp IS INITIAL AND p_filemp IS INITIAL AND p_filecr IS INITIAL
     AND NOT p_filetl IS INITIAL.
    v_flag = c_x.
    PERFORM zf_texto_longo.
  ELSE.
    PERFORM zf_monta_bapi.
  ENDIF.

  IF sy-batch = c_x.
    PERFORM zf_write_log.
  ELSE.
    PERFORM zf_exibe_alv.
  ENDIF.

*&---------------------------------------------------------------------*
*&      Form  ZF_VALIDA_PERFIL_ACESSO
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_valida_perfil_acesso .
  DATA: l_param   TYPE ztbbc_parametros-zvlpar.
  CLEAR:   t_empresa.
  REFRESH: t_empresa.

  SELECT zvlpar UP TO 1 ROWS
     FROM ztbbc_parametros
     INTO l_param
     WHERE programm EQ c_programm
       AND zparam   EQ c_bukrs.
  ENDSELECT.

  SPLIT l_param AT c_sep INTO TABLE t_empresa.

  LOOP AT t_empresa INTO w_empresa.
    AUTHORITY-CHECK OBJECT c_object
       ID 'C_ACTVT'  FIELD c_02
       ID 'C_BUKRS'  FIELD w_empresa-bukrs.
    IF sy-subrc <> 0.
      MESSAGE s000(oo) WITH text-t03 w_empresa DISPLAY LIKE 'E' .
    ENDIF.
  ENDLOOP.

ENDFORM.                    " ZF_VALIDA_PERFIL_ACESSO
*&---------------------------------------------------------------------*
*&      Form  ZF_LIMPAR_TAB_VAR
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_limpar_tab_var .
  CLEAR: t_cab,
         t_ope ,
         t_pac ,
         t_comp,
         t_map ,
         t_car ,
         t_text,
         t_log ,
         v_caminho,
         v_li.

  REFRESH: t_cab,
           t_ope ,
           t_pac ,
           t_comp,
           t_map ,
           t_car ,
           t_text,
           t_log .

ENDFORM.                    " ZF_LIMPAR_TAB_VAR
*&---------------------------------------------------------------------*
*&      Form  ZF_BUSCAR_ARQUIVO
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*      -->P_P_FILETL  text
*----------------------------------------------------------------------*
FORM zf_buscar_arquivo  USING p_filen  LIKE rlgrap-filename.

  CALL FUNCTION 'KD_GET_FILENAME_ON_F4'
    EXPORTING
      mask          = c_csv
      static        = c_x
    CHANGING
      file_name     = p_filen
    EXCEPTIONS
      mask_too_long = 1
      OTHERS        = 2.
  IF sy-subrc <> 0.
    sy-msgty = c_i.
    MESSAGE ID     sy-msgid
            TYPE   sy-msgty
            NUMBER sy-msgno
            WITH   sy-msgv1 sy-msgv2 sy-msgv3 sy-msgv4.
    STOP.
  ENDIF.
ENDFORM.                    " ZF_BUSCAR_ARQUIVO
*&---------------------------------------------------------------------*
*&      Form  ZF_VERIFICA_WIN_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_verifica_win_unix .

  IF p_locl EQ c_x.
*   Carrega arquivo do Windows
    PERFORM zf_carregar_tabela_win.
  ELSE .
*   Carrega arquivo do UNIX
    PERFORM zf_carregar_tabela_unix.
  ENDIF.

* Split dos arquivos
  PERFORM zf_split_arquivos.

ENDFORM.                    " ZF_VERIFICA_WIN_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGAR_TABELA_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carregar_tabela_win .
* Carrega tabela de cabeçalho
  PERFORM zf_carrega_cabecalho_win.
* Carrega tabela de operações
  PERFORM zf_carrega_operacoes_win.
* Carrega tabela de pacotes
  PERFORM zf_carrega_pacotes_win.
* Carrega tabela de componentes
  PERFORM zf_carrega_componentes_win.
* Carrega tabelade maps
  PERFORM zf_carrrega_maps_win.
* Carrega tabela de caracteristicas
  PERFORM zf_carrega_caracteristicas_win.
* Carrega tabela de textos longs
  PERFORM zf_carrega_textoslongos_win.
ENDFORM.                    " ZF_CARREGAR_TABELA_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_CABECALHO_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_cabecalho_win .
  CLEAR: v_caminho.
  MOVE p_filecb TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_cab_arq[].
ENDFORM.                    " ZF_CARREGA_CABECALHO_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_OPERACOES_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_operacoes_win .
  CLEAR: v_caminho.
  MOVE p_fileop TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_ope_arq[].
ENDFORM.                    " ZF_CARREGA_OPERACOES_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_PACOTES_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_pacotes_win .
  CLEAR: v_caminho.
  MOVE p_filept TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_pac_arq[].
ENDFORM.                    " ZF_CARREGA_PACOTES_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_COMPONENTES_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_componentes_win .
  CLEAR: v_caminho.
  MOVE p_filecp TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_comp_arq[].
ENDFORM.                    " ZF_CARREGA_COMPONENTES_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARRREGA_MAPS_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrrega_maps_win .
  CLEAR: v_caminho.
  MOVE p_filemp TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_map_arq[].
ENDFORM.                    " ZF_CARRREGA_MAPS_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_CARACTERISTICAS_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_caracteristicas_win .
  CLEAR: v_caminho.
  MOVE p_filecr TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_car_arq[].
ENDFORM.                    " ZF_CARREGA_CARACTERISTICAS_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_TEXTOSLONGOS_WIN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_textoslongos_win .
  CLEAR: v_caminho.
  MOVE p_filetl TO v_caminho.
* Processa gui-upload
  PERFORM zf_processar_gui.
  MOVE: t_arq[] TO t_text_arq[].
ENDFORM.                    " ZF_CARREGA_TEXTOSLONGOS_WIN
*&---------------------------------------------------------------------*
*&      Form  ZF_PROCESSAR_GUI
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_processar_gui .
  CLEAR : t_arq[].
  IF v_caminho IS NOT INITIAL.
    CALL FUNCTION 'GUI_UPLOAD'
      EXPORTING
        filename                = v_caminho
        has_field_separator     = 'X'
      TABLES
        data_tab                = t_arq
      EXCEPTIONS
        file_open_error         = 1
        file_read_error         = 2
        no_batch                = 3
        gui_refuse_filetransfer = 4
        invalid_type            = 5
        no_authority            = 6
        unknown_error           = 7
        bad_data_format         = 8
        header_not_allowed      = 9
        separator_not_allowed   = 10
        header_too_long         = 11
        unknown_dp_error        = 12
        access_denied           = 13
        dp_out_of_memory        = 14
        disk_full               = 15
        dp_timeout              = 16
        OTHERS                  = 17.
    IF sy-subrc <> 0.
      sy-msgty = c_i.
      MESSAGE ID     sy-msgid
              TYPE   sy-msgty
              NUMBER sy-msgno
              WITH   sy-msgv1 sy-msgv2 sy-msgv3 sy-msgv4.
      STOP.
    ENDIF.
  ENDIF.

ENDFORM.                    " ZF_PROCESSAR_GUI
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGAR_TABELA_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carregar_tabela_unix .
* Carrega tabela de cabeçalho
  PERFORM zf_carrega_cabecalho_unix.
* Carrega tabela de operações
  PERFORM zf_carrega_operacoes_unix.
* Carrega tabela de pacotes
  PERFORM zf_carrega_pacotes_unix.
* Carrega tabela de componentes
  PERFORM zf_carrega_componentes_unix.
* Carrega tabelade maps
  PERFORM zf_carrrega_maps_unix.
* Carrega tabela de caracteristicas
  PERFORM zf_carrega_caract_unix.
* Carrega tabela de textos longs
  PERFORM zf_carrega_texlongos_unix.

ENDFORM.                    " ZF_CARREGAR_TABELA_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_CABECALHO_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_cabecalho_unix .
  CLEAR: v_caminho.
  MOVE p_filecb TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_cab_arq[].
ENDFORM.                    " ZF_CARREGA_CABECALHO_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_OPERACOES_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_operacoes_unix .
  CLEAR: v_caminho.
  MOVE p_fileop TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_ope_arq[].
ENDFORM.                    " ZF_CARREGA_OPERACOES_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_PACOTES_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_pacotes_unix .
  CLEAR: v_caminho.
  MOVE p_filept TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_pac_arq[].
ENDFORM.                    " ZF_CARREGA_PACOTES_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_COMPONENTES_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_componentes_unix .
  CLEAR: v_caminho.
  MOVE p_filecp TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_comp_arq[].
ENDFORM.                    " ZF_CARREGA_COMPONENTES_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARRREGA_MAPS_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrrega_maps_unix .
  CLEAR: v_caminho.
  MOVE p_filemp TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_map_arq[].
ENDFORM.                    " ZF_CARRREGA_MAPS_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_CARACT_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_caract_unix .
  CLEAR: v_caminho.
  MOVE p_filecr TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_car_arq[].
ENDFORM.                    " ZF_CARREGA_CARACT_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_TEXLONGOS_UNIX
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_texlongos_unix .
  CLEAR: v_caminho.
  MOVE p_filetl TO v_caminho.
* Processa Open Dataset
  PERFORM zf_processar_open.
  MOVE: t_arq[] TO t_text_arq[].
ENDFORM.                    " ZF_CARREGA_TEXLONGOS_UNIX
*&---------------------------------------------------------------------*
*&      Form  ZF_PROCESSAR_OPEN
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_processar_open .
  OPEN DATASET v_caminho FOR INPUT IN TEXT MODE ENCODING DEFAULT.
  IF NOT sy-subrc IS INITIAL .
    MESSAGE s000(oo) WITH text-t03 DISPLAY LIKE 'E'.  "Erro ao abrir o arquivo.
    STOP.
  ENDIF.
  WHILE sy-subrc = 0.
    READ DATASET v_caminho INTO w_arq.
    IF sy-subrc = 0.
      APPEND w_arq TO t_arq.
      CLEAR w_arq.
    ENDIF.
  ENDWHILE.
  CLOSE DATASET v_caminho.
ENDFORM.                    " ZF_PROCESSAR_OPEN
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_ARQUIVOS
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_arquivos .
* Split do Cabeçalho
  PERFORM zf_split_cabecalho.

* Carrega tabela de operações
  PERFORM zf_split_operacoes.

* Carrega tabela de pacotes
  PERFORM zf_split_pacotes.

* Carrega tabela de componentes
  PERFORM zf_split_componentes.

* Carrega tabelade maps
  PERFORM zf_split_maps.

* Carrega tabela de caracteristicas
  PERFORM zf_split_caract.

* Carrega tabela de textos longs
  PERFORM zf_split_texlongos.
ENDFORM.                    " ZF_SPLIT_ARQUIVOS
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_CABECALHO
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_cabecalho .
  CLEAR v_li.
  LOOP AT t_cab_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                          w_cab-plnnr
                          w_cab-equnr
                          w_cab-tplnr
                          w_cab-datuv
                          w_cab-plnal
                          w_cab-ktext
                          w_cab-werk
                          w_cab-arbpl
                          w_cab-werks
                          w_cab-verwe
                          w_cab-vagrp
                          w_cab-statu
                          w_cab-anlzu
                          w_cab-strat
                          w_cab-istru
                          w_cab-slwbez
                          w_cab-profidnetz.
    APPEND w_cab TO t_cab.
    CLEAR: w_cab.
  ENDLOOP.

  IF NOT t_cab[] IS INITIAL.
    SELECT equnr_de equnr_para
      INTO TABLE t_equip
      FROM ztbpm_eqp_depara
      FOR ALL ENTRIES IN t_cab
      WHERE equnr_de = t_cab-equnr.
  ENDIF.

ENDFORM.                    " ZF_SPLIT_CABECALHO
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_OPERACOES
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_operacoes .
  CLEAR v_li.
  LOOP AT t_ope_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_ope-plnnr
                      w_ope-plnal
                      w_ope-vornr
                      w_ope-uvorn
                      w_ope-arbpl
                      w_ope-steus
                      w_ope-ltxa1
                      w_ope-arbei
                      w_ope-arbeh
                      w_ope-anzzl
                      w_ope-dauno
                      w_ope-daune
                      w_ope-indet
                      w_ope-prznt
                      w_ope-vertn
                      w_ope-aufkt
                      w_ope-larnt
                      w_ope-ktsch
                      w_ope-istru
                      w_ope-loanz
                      w_ope-logrp
                      w_ope-qualf
                      w_ope-kzlgf
                      w_ope-bmvrg
                      w_ope-bmeih
                      w_ope-preis
                      w_ope-peinh
                      w_ope-plifz
                      w_ope-sakto
                      w_ope-matkl
                      w_ope-ekgrp
                      w_ope-lifnr
                      w_ope-ekorg
                      w_ope-sortl
                      w_ope-srvpos
                      w_ope-ktext1
                      w_ope-menge
                      w_ope-meins
                      w_ope-tbtwr
                      w_ope-slwid
                      w_ope-usr00.

    IF w_ope-steus = c_pm03.
      CLEAR :w_ope-arbei,
             w_ope-arbeh.
    ENDIF.
    APPEND w_ope TO t_ope.
    CLEAR: w_ope.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_OPERACOES
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_PACOTES
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_pacotes .
  CLEAR v_li.
  LOOP AT t_pac_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_pac-plnnr
                      w_pac-plnal
                      w_pac-vornr
                      w_pac-uvorn
                      w_pac-paket.

    APPEND w_pac TO t_pac.
    CLEAR: w_pac.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_PACOTES
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_COMPONENTES
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_componentes .
  CLEAR v_li.
  LOOP AT t_comp_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_comp-plnnr
                      w_comp-plnal
                      w_comp-vornr
                      w_comp-uvorn
                      w_comp-idnrk
                      w_comp-menge
                      w_comp-meins
                      w_comp-rgekz
                      w_comp-disp.

    APPEND w_comp TO t_comp.
    CLEAR: w_comp.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_COMPONENTES
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_MAPS
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_maps .
  CLEAR v_li.
  LOOP AT t_map_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_map-plnnr
                      w_map-plnal
                      w_map-vornr
                      w_map-uvorn
                      w_map-psnfh
                      w_map-matnr
                      w_map-werks
                      w_map-mgvgw
                      w_map-equnr
                      w_map-steuf.

    APPEND w_map TO t_map.
    CLEAR: w_map.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_MAPS
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_CARACT
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_caract .
  CLEAR v_li.
  LOOP AT t_car_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_car-plnnr
                      w_car-plnal
                      w_car-vornr
                      w_car-uvorn
                      w_car-merknr
                      w_car-verwmerkm
                      w_car-qpmk_zaehl
                      w_car-mkversion
                      w_car-kurztext
                      w_car-pmethode
                      w_car-qmtb_werks
                      w_car-pmtversion
                      w_car-stichprver
                      w_car-probenr
                      w_car-pruefquali
                      w_car-eeantverf
                      w_car-merkgew
                      w_car-charact_id1
                      w_car-qergdath
                      w_car-dummy10
                      w_car-dummy20
                      w_car-dummy40
                      w_car-stellen
                      w_car-masseinhsw
                      w_car-sollwert
                      w_car-toleranzun
                      w_car-toleranzob
                      w_car-plausiunte
                      w_car-plausioben
                      w_car-formel1
                      w_car-formel2
                      w_car-katalgart2
                      w_car-auswmenge2
                      w_car-auswmgwrk2
                      w_car-codegrqual
                      w_car-codequal
                      w_car-codegr9o
                      w_car-code9o
                      w_car-codegr9u
                      w_car-code9u.

    APPEND w_car TO t_car.
    CLEAR: w_car.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_CARACT
*&---------------------------------------------------------------------*
*&      Form  ZF_SPLIT_TEXLONGOS
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_split_texlongos .
  CLEAR v_li.
  LOOP AT t_text_arq INTO v_li.
    SPLIT v_li AT ';' INTO
                      w_text-plnnr
                      w_text-plnal
                      w_text-werks
                      w_text-vornr
                      w_text-uvorn
*                      w_text-ltxa1
                      w_text-caminho.
*    UNPACK w_text-plnnr TO w_text-plnnr.

    APPEND w_text TO t_text.
    CLEAR: w_text.
  ENDLOOP.
ENDFORM.                    " ZF_SPLIT_TEXLONGOS

*&---------------------------------------------------------------------*
*&      Form  ZF_VERIFICA_EQUI
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_verifica_equi .

  READ TABLE t_equip INTO w_equip WITH KEY equnr_de = w_cab-equnr.
  IF sy-subrc = 0.
    w_cab-equnr = w_equip-equnr_para.
  ENDIF.

ENDFORM.                    " ZF_VERIFICA_EQUI


*&---------------------------------------------------------------------*
*&      Form  ZF_PREENCHE_BDCDATA
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*      -->P_1949   text
*      -->P_1950   text
*      -->P_1951   text
*----------------------------------------------------------------------*
FORM zf_preenche_bdcdata USING l_start TYPE c
                               l_name  TYPE c
                               l_value TYPE any.

  MOVE l_start TO t_bdc-dynbegin.
  IF l_start = c_x.
    MOVE:
      l_name  TO t_bdc-program,
      l_value TO t_bdc-dynpro.
  ELSE.
    MOVE:
      l_name  TO t_bdc-fnam,
      l_value TO t_bdc-fval.
  ENDIF.
  APPEND t_bdc.
  CLEAR t_bdc.

ENDFORM.                    " ZF_PREENCHE_BDCDATA


*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_LOG
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_log .
  DATA: l_mesg TYPE char255,
      l_status TYPE c,
      l_msgno TYPE sy-msgno.

  IF NOT t_messtab[] IS INITIAL.
    LOOP AT t_messtab.
      CLEAR: l_msgno.

      l_msgno = t_messtab-msgnr.
      CALL FUNCTION 'WRITE_MESSAGE'
        EXPORTING
          msgid = t_messtab-msgid
          msgno = l_msgno
          msgty = t_messtab-msgtyp
        IMPORTING
          messg = v_mesg.

      IF v_mesg IS NOT INITIAL. "AND t_messtab-MSGTYP <> c_w.

        IF v_mesg-msgty = c_s AND v_mesg-msgno = c_120.
          w_log-plnnr  = t_messtab-msgv1.
        ELSE.
          w_log-plnnr = w_cab_aux-plnnr.
        ENDIF.
        w_log-messg  = v_mesg-msgtx.
        APPEND w_log TO t_log.
        CLEAR: w_log, v_mesg.
      ENDIF.

    ENDLOOP.
  ENDIF.
ENDFORM.                    " ZF_MONTA_LOG
*&---------------------------------------------------------------------*
*&      Form  ZF_EXIBE_ALV
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_exibe_alv .
  w_layout-colwidth_optimize = c_x.
  w_layout-zebra             = c_x.

  CLEAR w_fieldcat.
  w_fieldcat-fieldname = c_plnnr. "PLNNR
  w_fieldcat-col_pos = 1.
  w_fieldcat-reptext_ddic  = text-t05.
  APPEND w_fieldcat TO t_fieldcat.

  CLEAR w_fieldcat.
  w_fieldcat-fieldname = c_messg. " MESSG.
  w_fieldcat-col_pos = 2.
  w_fieldcat-reptext_ddic  = text-t06."'Mensagem
  APPEND w_fieldcat TO t_fieldcat.


  CALL FUNCTION 'REUSE_ALV_GRID_DISPLAY'
    EXPORTING
      i_callback_program = sy-repid
      is_layout          = w_layout
      it_fieldcat        = t_fieldcat[]
      i_default          = c_x
    TABLES
      t_outtab           = t_log
    EXCEPTIONS
      program_error      = 1
      OTHERS             = 2.
  IF sy-subrc <> 0.
* Implement suitable error handling here
  ENDIF.

ENDFORM.                    " ZF_EXIBE_ALV
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_BAPI
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_bapi .
  DATA: l_tabix  TYPE sy-tabix.

  CLEAR: w_cab, w_comp, w_map, w_car, w_text, w_ope,
         w_comp_aux, w_map_aux,  w_ope_aux.
  CLEAR : w_ope_bapi, w_comp_bapi, w_map_bapi, w_serv_bapi, w_pac_bapi.
  REFRESH: t_ope_bapi, t_comp_bapi, t_map_bapi, t_serv_bapi, t_pac_bapi.



  LOOP AT t_cab INTO w_cab.

    REFRESH: t_text_l_bapi[], t_text_l_bapi[].
    CLEAR: w_cab_bapi, w_ope_bapi, w_map_bapi, w_pac_bapi, w_comp_bapi.
    CLEAR: t_bdc.


* verifica equipamento
    PERFORM zf_verifica_equi.

* Verifica campos obrigatorios do cabeçalho.
    IF w_cab-plnnr = space OR w_cab-datuv = space OR
       w_cab-plnal = space OR w_cab-ktext = space OR
       w_cab-werks = space OR w_cab-verwe = space OR
       w_cab-statu = space OR w_cab-profidnetz = space.

      w_log-plnnr = w_cab-plnnr.
      w_log-messg = text-t04.
      APPEND w_log TO t_log.
      CLEAR w_log.
      CONTINUE.
    ENDIF.

* Preenche o PLNTY

    PERFORM zf_preenche_header.
*início carrega texto longo para cabeçalho.
    w_text_bapi-textstart = w_text_bapi-textend    + '00000001'.
    w_text_bapi-textend   = w_text_bapi-textstart  + '00000001'.
    w_text_bapi-plnty     = w_cab_bapi-plnty.
    w_text_bapi-langu     = sy-langu.
    w_text_bapi-langu_iso = sy-langu.
    APPEND w_text_bapi TO t_text_bapi.


    w_l_bapi-tdformat = '*'.
    w_l_bapi-tdline   = w_cab-ktext.
    APPEND w_l_bapi TO t_text_l_bapi.

    w_l_bapi-tdformat = '*'.
*    w_l_bapi-tdline   = 'Ativa texto longo '.
    w_l_bapi-tdline   = ' '.
    APPEND w_l_bapi TO t_text_l_bapi.
*fim carrega texto longo para cabeçalho.

    CLEAR: l_tabix.
    SORT t_ope BY plnnr plnal.
    READ TABLE t_ope INTO w_ope_aux WITH KEY  plnnr = w_cab-plnnr
                                              plnal = w_cab-plnal.
    IF sy-subrc IS INITIAL.
      l_tabix = sy-tabix.
      LOOP AT t_ope INTO w_ope FROM l_tabix.

* verificação de campo obrigatorio
        IF w_ope-plnnr <> w_ope_aux-plnnr.
          EXIT.
        ELSEIF w_ope-plnnr = space OR w_ope-plnal = space.
          w_log-plnnr = w_cab-plnnr.
          w_log-messg = text-t04.
          APPEND w_log TO t_log.
          CLEAR w_log.
          CONTINUE.
        ENDIF.

        IF w_ope-vornr = space OR w_ope-arbpl = space OR
        w_ope-steus = space OR w_ope-ltxa1 = space OR
        w_ope-arbeh = space OR w_ope-anzzl = space OR
        w_ope-dauno = space OR w_ope-daune = space.
          w_log-plnnr = w_cab-plnnr.
          w_log-messg = text-t04.
          APPEND w_log TO t_log.
          CLEAR w_log.
          CONTINUE.
        ENDIF.

* Monta operação
        PERFORM zf_monta_ope.
***início carrega texto longo para operação***
***início de texto inicial para texto longo
        w_text_bapi-textstart = w_text_bapi-textend    + '00000001'.
        w_text_bapi-textend   = w_text_bapi-textstart  + '00000001'.
        w_text_bapi-plnty     = w_cab_bapi-plnty.
        w_text_bapi-langu     = sy-langu.
        w_text_bapi-langu_iso = sy-langu.
        w_text_bapi-vornr     = w_ope-vornr.
        APPEND w_text_bapi TO t_text_bapi.


        w_l_bapi-tdformat = '*'.
        w_l_bapi-tdline   = w_ope-ltxa1.
        APPEND w_l_bapi TO t_text_l_bapi.

        w_l_bapi-tdformat = '*'.
*        w_l_bapi-tdline   = 'Ativa texto longo '.
        w_l_bapi-tdline   = ' '.
        APPEND w_l_bapi TO t_text_l_bapi.
***fim de texto inicial para texto longo
***fim carrega texto longo para operação***
        w_ope_aux = w_ope.
      ENDLOOP.

    ENDIF.

* trata tabela de map para passar para bapi.
    CLEAR: l_tabix.
    SORT t_map BY plnnr plnal.
    READ TABLE t_map INTO w_map_aux WITH KEY  plnnr = w_cab-plnnr
                                              plnal = w_cab-plnal.
    IF sy-subrc IS INITIAL.
      l_tabix = sy-tabix.
      LOOP AT t_map INTO w_map FROM l_tabix.
        IF w_map-plnnr <> w_map_aux-plnnr.
          EXIT.
        ENDIF.
        PERFORM zf_monta_maps.
      ENDLOOP.
    ENDIF.


* verificar componentes
    CLEAR: l_tabix.
    SORT t_comp BY plnnr plnal.
    READ TABLE t_comp INTO w_comp_aux WITH KEY  plnnr = w_cab-plnnr
                                                plnal = w_cab-plnal.
    IF sy-subrc IS INITIAL.
      l_tabix = sy-tabix.
      LOOP AT t_comp INTO w_comp  FROM l_tabix.
        IF w_comp-plnnr <> w_comp_aux-plnnr.
          EXIT.
        ENDIF.
        PERFORM zf_monta_componentes.
      ENDLOOP.
    ENDIF.

* Monta pacotes.

    CLEAR: l_tabix.
    SORT t_pac BY plnnr plnal.
    READ TABLE t_pac INTO w_pac_aux WITH KEY  plnnr = w_cab-plnnr
                                              plnal = w_cab-plnal.
    IF sy-subrc IS INITIAL.
      l_tabix = sy-tabix.
      LOOP AT t_pac INTO w_pac FROM l_tabix.
        IF w_pac-plnnr <> w_pac_aux-plnnr.
          EXIT.
        ENDIF.
        PERFORM zf_monta_pac.
      ENDLOOP.
    ENDIF.


    PERFORM zf_chama_bapi.

* Perform grava novo PLNNR.
    PERFORM zf_salva_novo_plnnr.

** Monta log
*    PERFORM zf_monta_log.
    CLEAR: w_cab, w_comp, w_map, w_car, w_text, w_ope,
           w_comp_aux, w_map_aux, w_ope_aux, v_plnnr, v_plnty.

  ENDLOOP. " Loop tabela cabeçalho

ENDFORM.                    " ZF_MONTA_BAPI
*&---------------------------------------------------------------------*
*&      Form  ZF_PREENCHE_HEADER
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_preenche_header .
  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = w_cab-equnr
    IMPORTING
      output = w_cab-equnr.

  CLEAR : v_plnty.

  IF w_cab-equnr IS NOT INITIAL.
    w_cab_bapi-plnty = c_e.
    v_plnty = c_e.
  ELSEIF w_cab-tplnr IS NOT INITIAL.
    w_cab_bapi-plnty = c_t.
    v_plnty = c_t.
  ELSE.
    w_cab_bapi-plnty = c_a.
    v_plnty = c_a.
  ENDIF.

*  w_cab_bapi-plnnr = w_cab-plnnr.
*  w_cab_bapi-plnty = w_cab-plnty.
  w_cab_bapi-plnal = w_cab-plnal.
  w_cab_bapi-equnr = w_cab-equnr.
  w_cab_bapi-tplnr = w_cab-tplnr.
  w_cab_bapi-datuv = w_cab-datuv.
*w_cab_bapi-AENNR = w_cab-.
  w_cab_bapi-verwe = w_cab-verwe.
  w_cab_bapi-werks = w_cab-werks.
  w_cab_bapi-statu = w_cab-statu.
  w_cab_bapi-vagrp = w_cab-vagrp.
  w_cab_bapi-ktext = w_cab-ktext.
  w_cab_bapi-strat = w_cab-strat.
  w_cab_bapi-istru = w_cab-istru.
*w_cab_bapi-IWERK = w_cab-.
  w_cab_bapi-anlzu = w_cab-anlzu.
*w_cab_bapi-EXTNUM = w_cab.
*w_cab_bapi-DELKZ = w_cab.
  w_cab_bapi-slwbez = w_cab-slwbez.
*w_cab_bapi-ADPSP = w_cab.
  w_cab_bapi-arbpl = w_cab-arbpl.
*w_cab_bapi-ARBPL_WERK = w_cab.
*w_cab_bapi-XHIERTL = w_cab.
*w_cab_bapi-TL_EXTID = w_cab.
*  v_plnty = w_cab_bapi-plnty.



ENDFORM.                    " ZF_PREENCHE_HEADER
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_OPE
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_ope .
  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = w_ope-lifnr
    IMPORTING
      output = w_ope-lifnr.

  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = w_ope-sakto
    IMPORTING
      output = w_ope-sakto.

  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = w_ope-ktsch
    IMPORTING
      output = w_ope-ktsch.

  w_ope_bapi-plnty = w_cab_bapi-plnty .  " tipo de lista
*  w_ope_bapi-PLNNR = w_ope-plnnr.
  w_ope_bapi-plnal = w_ope-plnal.
*w_ope_bapi-PLNKN = w_ope-p
  w_ope_bapi-vornr = w_ope-vornr.
  w_ope_bapi-uvorn = w_ope-uvorn.

  w_ope_bapi-steus = w_ope-steus.
  w_ope_bapi-arbpl = w_ope-arbpl.
  w_ope_bapi-werks = w_cab_bapi-werks.


  w_ope_bapi-ktsch = w_ope-ktsch.
  w_ope_bapi-ltxa1 = w_ope-ltxa1.
*w_ope_bapi-TXTSP
  w_ope_bapi-loanz = w_ope-loanz.
*w_ope_bapi-LOART = w_ope-loart.
  w_ope_bapi-qualf = w_ope-qualf.
  w_ope_bapi-logrp = w_ope-logrp.
  w_ope_bapi-sortl = w_ope-sortl.
  w_ope_bapi-lifnr = w_ope-lifnr.
  w_ope_bapi-bmeih = w_ope-bmeih.
  w_ope_bapi-bmvrg = w_ope-bmvrg.
  w_ope_bapi-preis = w_ope-preis.
  w_ope_bapi-peinh = w_ope-peinh.
  w_ope_bapi-sakto = w_ope-sakto.
*w_ope_bapi-WAERS = w_ope-waers.
*w_ope_bapi-INFNR = w_ope-l
  w_ope_bapi-ekorg = w_ope-ekorg.
  w_ope_bapi-ekgrp = w_ope-ekgrp.
  w_ope_bapi-matkl = w_ope-matkl.
  w_ope_bapi-anzzl = w_ope-anzzl.
  w_ope_bapi-prznt = w_ope-prznt.
  w_ope_bapi-indet = w_ope-indet.
  w_ope_bapi-larnt = w_ope-larnt.
*w_ope_bapi-ANLZU = w_ope-anlzu.
  w_ope_bapi-istru = w_ope-istru.
*w_ope_bapi-VERTL = w_ope-vertl.
  w_ope_bapi-plifz = w_ope-plifz.
  w_ope_bapi-dauno = w_ope-dauno.
  w_ope_bapi-daune = w_ope-daune.
*w_ope_bapi-EINSA
*w_ope_bapi-EINSE
  IF w_ope-steus = c_pm03.
    CLEAR :w_ope_bapi-arbei,
           w_ope_bapi-arbeh.
  ENDIF.
  w_ope_bapi-arbei = w_ope-arbei.
  w_ope_bapi-arbeh = w_ope-arbeh.

  w_ope_bapi-slwid = w_ope-slwid.
  w_ope_bapi-aufkt = w_ope-aufkt.
  w_ope_bapi-usr00 = w_ope-usr00.

*  w_ope_bapi-ltxa2 = C_X.  " teste
  w_ope_bapi-txtsp = sy-langu.

  APPEND w_ope_bapi TO t_ope_bapi.
  CLEAR w_ope_bapi.

  IF NOT w_ope-srvpos IS INITIAL.
    w_serv_bapi-plnty = w_cab_bapi-plnty.
    w_serv_bapi-plnal  = w_ope-plnal.
    w_serv_bapi-vornr = w_ope-vornr.
    w_serv_bapi-srv_line = c_10.
    w_serv_bapi-service = w_ope-srvpos.
    w_serv_bapi-short_text = w_ope-ktext1.
    w_serv_bapi-quantity = w_ope-menge.
    w_serv_bapi-uom = w_ope-meins.
    w_serv_bapi-gross_price = w_ope-tbtwr.
    APPEND w_serv_bapi TO t_serv_bapi.
    CLEAR : w_serv_bapi.

  ENDIF.


ENDFORM.                    " ZF_MONTA_OPE
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_PAC
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_pac .
  w_pac_bapi-plnty  = w_cab_bapi-plnty.
*  w_pac_bapi-PLNNR  = w_pac-PLNNR.
  w_pac_bapi-plnal  = w_pac-plnal.
*w_map_bapi-PLNKN  = w_
  w_pac_bapi-paket  = w_pac-paket.
  w_pac_bapi-vornr  = w_pac-vornr.
*w_pac_bapi-STRAT  = w_pac-strat.
  APPEND w_pac_bapi TO t_pac_bapi.
  CLEAR w_pac_bapi.
ENDFORM.                    " ZF_MONTA_PAC
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_COMPONENTES
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_componentes .
  CALL FUNCTION 'CONVERSION_EXIT_MATN1_INPUT'
    EXPORTING
      input        = w_comp-idnrk
    IMPORTING
      output       = w_comp-idnrk
    EXCEPTIONS
      length_error = 1
      OTHERS       = 2.
  IF sy-subrc <> 0.
* Implement suitable error handling here
  ENDIF.


  w_comp_bapi-plnty = w_cab_bapi-plnty.
*  w_comp_bapi-PLNNR = w_comp-plnnr.
  w_comp_bapi-plnal = w_comp-plnal.
*w_comp_bapi-PLNKN =
*w_comp_bapi-ZUONR =
  w_comp_bapi-vornr = w_comp-vornr.
  w_comp_bapi-idnrk = w_comp-idnrk.
  w_comp_bapi-rgekz = w_comp-rgekz.
  w_comp_bapi-disp = w_comp-disp.
  w_comp_bapi-menge = w_comp-menge.
  w_comp_bapi-meins = w_comp-meins.
*w_comp_bapi-STLTY = w_comp-
*w_comp_bapi-STLNR
*w_comp_bapi-STLAL
*w_comp_bapi-STLKN
  APPEND w_comp_bapi TO t_comp_bapi.
  CLEAR w_comp_bapi.
ENDFORM.                    " ZF_MONTA_COMPONENTES
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_MAPS
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_maps .

  CALL FUNCTION 'CONVERSION_EXIT_MATN1_INPUT'
    EXPORTING
      input        = w_map-matnr
    IMPORTING
      output       = w_map-matnr
    EXCEPTIONS
      length_error = 1
      OTHERS       = 2.
  IF sy-subrc <> 0.
* Implement suitable error handling here
  ENDIF.

  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = w_map-equnr
    IMPORTING
      output = w_map-equnr.

  w_map_bapi-plnty = w_cab_bapi-plnty.
  w_map_bapi-plnal = w_cab-plnal.
  w_map_bapi-vornr = w_map-vornr.
  w_map_bapi-psnfh = w_map-psnfh.
  w_map_bapi-steuf = w_map-steuf.
  w_map_bapi-mgvgw = w_map-mgvgw.
  w_map_bapi-fhwrk = w_map-werks.
  w_map_bapi-matnr = w_map-matnr.
  w_map_bapi-equnr = w_map-equnr.
  IF w_map_bapi-equnr IS NOT INITIAL.
    w_map_bapi-fhmar = c_e.
  ELSEIF w_map_bapi-matnr IS NOT INITIAL.
    w_map_bapi-fhmar = c_m.
  ENDIF.
  APPEND w_map_bapi TO t_map_bapi.
  CLEAR w_map_bapi.
ENDFORM.                    " ZF_MONTA_MAPS
*&---------------------------------------------------------------------*
*&      Form  ZF_CHAMA_BAPI
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_chama_bapi .
  DATA: l_tabix TYPE sy-tabix,
        l_perfil TYPE char7.

  l_perfil = w_cab-profidnetz.
  TRANSLATE l_perfil TO UPPER CASE.
  CONDENSE l_perfil.

  CALL FUNCTION 'EAM_TASKLIST_CREATE'
    EXPORTING
      is_header                = w_cab_bapi
      iv_date                  = sy-datum
      iv_profile               = l_perfil
      iv_clear_buffer_if_error = c_x
      iv_update_shorttext      = c_x
    IMPORTING
      ev_plnnr                 = v_plnnr
      ev_plnal                 = v_plnal
    TABLES
      it_operations            = t_ope_bapi
      it_components            = t_comp_bapi
      it_prts                  = t_map_bapi
      it_spack_lines           = t_serv_bapi
      it_mpackages             = t_pac_bapi
      it_text                  = t_text_bapi   " header do texto longo
      it_text_lines            = t_text_l_bapi " linhas.
      et_return                = t_return_cre.

  PERFORM zf_monta_log_bapi.



  IF NOT v_plnnr IS INITIAL.
    CALL FUNCTION 'EAM_TASKLIST_POST'
      EXPORTING
        iv_plnty  = w_cab_bapi-plnty
        iv_plnnr  = v_plnnr
      IMPORTING
        et_return = t_return_cre.

    PERFORM zf_monta_log_bapi.

    CALL FUNCTION 'BAPI_TRANSACTION_COMMIT'
      EXPORTING
        wait   = c_x
      IMPORTING
        return = w_return_cre.

    IF sy-subrc = 0.
*      PERFORM zf_texto_longo.
      PERFORM zf_monta_log.
      CLEAR: l_tabix.
      SORT t_car BY plnnr plnal.
      READ TABLE t_car INTO w_car_aux WITH KEY  plnnr = w_cab-plnnr
                                                plnal = w_cab-plnal.
      IF sy-subrc IS INITIAL.
        l_tabix = sy-tabix.
        LOOP AT t_car INTO w_car  FROM l_tabix.
          IF w_car-plnnr <> w_car_aux-plnnr.
            EXIT.
          ENDIF.
          PERFORM zf_monta_caracteristica.

        ENDLOOP.
      ENDIF.
    ENDIF.
  ENDIF.
ENDFORM.                    " ZF_CHAMA_BAPI
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_CARACTERISTICA
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_caracteristica .
*IA06 = lista de tarefas geral (PLNTY = A)
*IA12 = lista de tarefas para local de instalação (PLNTY = T)
*IA02 = lista de tarefas para equipamentos (PLNTY = E)

  IF v_plnty = c_a.
    PERFORM zf_monta_lista_geral_a.
    PERFORM zf_chama_transaction USING c_ia06 v_modo c_s.

  ELSEIF v_plnty = c_t.
    PERFORM zf_monta_lista_tarefas_local_t.
    PERFORM zf_chama_transaction USING c_ia12 v_modo c_s.

  ELSEIF v_plnty = c_e.
    PERFORM zf_monta_lista_tarefas_equip_e.
    PERFORM zf_chama_transaction USING c_ia02 v_modo c_s.
  ENDIF.
  PERFORM zf_monta_log.
ENDFORM.                    " ZF_MONTA_CARACTERISTICA
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_LISTA_GERAL_A
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_lista_geral_a .
  DATA: l_data(8) TYPE c. "Formatar data

  CLEAR l_data.

  TRANSLATE w_cab-profidnetz TO UPPER CASE.

* colocar data no formato dia mes ano
  CONCATENATE sy-datum+6(2) sy-datum+4(2) sy-datum+0(4) INTO l_data.
* Executa bdc IA06
  PERFORM zf_preenche_bdcdata USING:
     'X'         'SAPLCPDI'             '3001',
     ' '         'BDC_CURSOR'           'RC271-PLNAL',"'RC271-STTAG',
     ' '         'BDC_OKCODE'           '=VOUE',
     ' '         'RC271-PLNNR'          v_plnnr,
     ' '         'RC271-PROFIDNETZ'     w_cab-profidnetz,
     ' '         'RC271-STTAG'          l_data,
     ' '         'RC271-WERKS'          w_cab-werks,
     ' '         'RC271-PLNAL'          ' '." w_cab_aux-plnal.

  PERFORM zf_preenche_bdcdata USING:
     'X'         'SAPLCPDI'             '3400',
*     ' '         'BDC_CURSOR'           'PLPOD-VORNR(01)',
     ' '         'BDC_OKCODE'           '=QMUE',
     ' '         'RC27X-FLG_SEL(01)'    c_x.

  PERFORM zf_preenche_bdcdata USING:
     'X'          'SAPLQPAA'                       '0150',
     ' '          'BDC_CURSOR'                     'PLMKB-MERKNR(01)',
     ' '          'BDC_OKCODE'                     '=QMEF',
     ' '          'RQPAS-SEL_FLG(01)'               c_x.

  PERFORM zf_preenche_bdcdata USING:
    'X'          'SAPLQPAA'                       '0150',
    ' '          'BDC_CURSOR'                     'PLMKB-MERKNR(01)',
    ' '          'BDC_OKCODE'                     '=QMAM',
*  ' '          'RQPAS-ENTRY_ACT'                w_car-entry_act,
    ' '          'PLMKB-MERKNR(01)'               w_car-merknr,
    ' '          'PLMKB-VERWMERKM(01)'            w_car-verwmerkm,
    ' '          'PLMKB-QPMK_WERKS(01)'           w_car-qmtb_werks,
    ' '          'PLMKB-MKVERSION(01)'            w_car-mkversion,
    ' '          'PLMKB-KURZTEXT(01)'             w_car-kurztext,
*  ' '          'PLMKB-TOLERANZSL(01)'           w_car-toleranzsl,
    ' '          'PLMKB-PMETHODE(01)'             w_car-pmethode,
*  ' '          'PLMKB-QMTB_WERKS(01)'           w_car-qmtb_werks,
    ' '          'PLMKB-PMTVERSION(01)'           w_car-pmtversion,
    ' '          'PLMKB-STICHPRVER(01)'           w_car-stichprver,
    ' '          'PLMKB-DUMMY10(01)'              w_car-dummy10,
    ' '          'PLMKB-DUMMY20(01)'              w_car-dummy20,
    ' '          'PLMKB-DUMMY40(01)'              w_car-dummy40,
    ' '          'RQPAS-SEL_FLG(01)'              c_x.

  PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1501',
      ' '          'BDC_CURSOR'                     'PLMKB-VERWMERKM',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-VERWMERKM'                w_car-verwmerkm,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-MKVERSION'                w_car-mkversion.

  IF w_car-formel1 IS NOT INITIAL.
    PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1522',
      ' '          'BDC_CURSOR'                     'PLMKB-FORMEL2',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-FORMELSL'                 c_x," w_car-formelsl,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-FORMEL1'                  w_car-formel1,
      ' '          'PLMKB-FORMEL2'                  w_car-formel2.
  ENDIF.

  PERFORM zf_preenche_bdcdata USING:
    'X'          'SAPLQPAA'                       '0160',
    ' '          'BDC_CURSOR'                     'PLMKB-FORMEL2',
    ' '          'BDC_OKCODE'                     '=QMNM',
    ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
    ' '          'PLMKB-PROBENR'                  w_car-probenr,
    ' '          'PLMKB-PRUEFQUALI'               w_car-pruefquali,
    ' '          'PLMKB-EEANTVERF'                w_car-eeantverf,
    ' '          'PLMKB-MERKGEW'                  w_car-merkgew,
    ' '          'PLMKB-QERGDATH'                 w_car-qergdath.

  PERFORM zf_preenche_bdcdata USING:
    'X'          'SAPLQPAA'                       '0160',
    ' '          'BDC_CURSOR'                     'QFLTP-PLAUSIOBEN',
    ' '          'BDC_OKCODE'                     '=QMLM',
    ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
    ' '          'PLMKB-STELLEN'                  w_car-stellen,
    ' '          'RQPAS-MASSEINHSW'               w_car-masseinhsw,
    ' '          'QFLTP-SOLLWERT'                 w_car-sollwert,
    ' '          'QFLTP-TOLERANZUN'               w_car-toleranzun,
    ' '          'QFLTP-TOLERANZOB'               w_car-toleranzob,
    ' '          'QFLTP-PLAUSIUNTE'               w_car-plausiunte,
    ' '          'QFLTP-PLAUSIOBEN'               w_car-plausioben.


  IF w_car-charact_id1 IS NOT INITIAL OR w_car-codegr9o IS NOT INITIAL OR
     w_car-code9o      IS NOT INITIAL OR w_car-codegr9u IS NOT INITIAL OR
     w_car-code9u      IS NOT INITIAL.

    IF w_car-stellen    IS NOT INITIAL OR w_car-masseinhsw IS NOT INITIAL OR
       w_car-sollwert   IS NOT INITIAL OR w_car-toleranzun IS NOT INITIAL OR
       w_car-toleranzun IS NOT INITIAL OR w_car-plausiunte IS NOT INITIAL OR
       w_car-plausioben IS NOT INITIAL.

      PERFORM zf_preenche_bdcdata USING:
       'X'          'SAPLQPAA'                       '0160',
       ' '          'BDC_CURSOR'                     'PLMKB-CODE9U',
       ' '          'BDC_OKCODE'                     '=QMBU',
       ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
       ' '          'PLMKB-KATALGART2'               w_car-katalgart2,
       ' '          'PLMKB-AUSWMENGE2'               w_car-auswmenge2,
       ' '          'PLMKB-AUSWMGWRK2'               w_car-auswmgwrk2,
       ' '          'PLMKB-CODEQUAL'                 w_car-codequal,
       ' '          'PLMKB-CODEGRQUAL'               w_car-codegrqual,
       ' '          'PLMKB-CODE9O'                   w_car-code9o,
       ' '          'PLMKB-CODEGR9O'                 w_car-codegr9o,
       ' '          'PLMKB-CODE9U'                   w_car-code9u,
       ' '          'PLMKB-CODEGR9U'                 w_car-codegr9u.


    ENDIF.
  ENDIF.

ENDFORM.                    " ZF_MONTA_LISTA_GERAL_A
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_LISTA_TAREFAS_LOCAL_T
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_lista_tarefas_local_t .
  DATA: l_data(8) TYPE c, "Formatar data
        l_flag   TYPE c.

  CLEAR: l_data, l_flag.

  TRANSLATE w_cab-profidnetz TO UPPER CASE.

* colocar data no formato dia mes ano
  CONCATENATE sy-datum+6(2) sy-datum+4(2) sy-datum+0(4) INTO l_data.

  PERFORM zf_preenche_bdcdata USING:
     'X'         'SAPLCPDI'             '3005',
     ' '         'BDC_CURSOR'           'RC271-PLNAL',
     ' '         'BDC_OKCODE'           '=VOUE',
     ' '         'RC27E-TPLNR'          v_plnnr,
     ' '         'RC271-PROFIDNETZ'     w_cab-profidnetz,
     ' '         'RC271-STTAG'          l_data,
     ' '         'RC271-PLNAL'          space.

  PERFORM zf_preenche_bdcdata USING:
    'X'         'SAPLCPDI'             '3400',
    ' '         'BDC_CURSOR'           'PLPOD-VORNR(01)',
    ' '         'BDC_OKCODE'           '=QMUE',
    ' '         'RC27X-FLG_SEL(01)'    c_x.

  PERFORM zf_preenche_bdcdata USING:
   'X'         'SAPLQPAA'             '0150',
   ' '         'BDC_CURSOR'           'PLMKB-MERKNR(01)',
   ' '         'BDC_OKCODE'           '=QMEF',
*     ' '         'RQPAS-ENTRY_ACT'      w_car-
   ' '         'RQPAS-SEL_FLG(01)'    c_x.

  PERFORM zf_preenche_bdcdata USING:
    'X'          'SAPLQPAA'                       '0150',
    ' '          'BDC_CURSOR'                     'PLMKB-DUMMY40(01)',
    ' '          'BDC_OKCODE'                     '=QMAM',
    ' '          'PLMKB-MERKNR(01)'               w_car-merknr,
    ' '          'PLMKB-VERWMERKM(01)'            w_car-verwmerkm,
    ' '          'PLMKB-QPMK_WERKS(01)'           w_car-qmtb_werks,
    ' '          'PLMKB-MKVERSION(01)'            w_car-mkversion,
    ' '          'PLMKB-KURZTEXT(01)'             w_car-kurztext,
    ' '          'PLMKB-PMETHODE(01)'             w_car-pmethode,
    ' '          'PLMKB-PMTVERSION(01)'           w_car-pmtversion,
    ' '          'PLMKB-STICHPRVER(01)'           w_car-stichprver,
    ' '          'PLMKB-DUMMY10(01)'              w_car-dummy10,
    ' '          'PLMKB-DUMMY20(01)'              w_car-dummy20,
    ' '          'PLMKB-DUMMY40(01)'              w_car-dummy40,
    ' '          'RQPAS-SEL_FLG(01)'              c_x.

  PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1501',
      ' '          'BDC_CURSOR'                     'PLMKB-VERWMERKM',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-VERWMERKM'                w_car-verwmerkm,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-MKVERSION'                w_car-mkversion.

  IF w_car-formel1 IS NOT INITIAL.
    PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1522',
      ' '          'BDC_CURSOR'                     'PLMKB-FORMEL1',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-FORMELSL'                 c_x," w_car-formelsl,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-FORMEL1'                  w_car-formel1,
      ' '          'PLMKB-FORMEL2'                  w_car-formel2.
    l_flag = c_x.
  ENDIF.

  IF l_flag IS NOT INITIAL.
    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-QERGDATH',
        ' '          'BDC_OKCODE'                     '=QMNM',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-PROBENR'                  w_car-probenr,
        ' '          'PLMKB-PRUEFQUALI'               w_car-pruefquali,
        ' '          'PLMKB-EEANTVERF'                w_car-eeantverf,
        ' '          'PLMKB-MERKGEW'                  w_car-merkgew,
        ' '          'PLMKB-QERGDATH'                 w_car-qergdath.

    PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '0160',
      ' '          'BDC_CURSOR'                     'QFLTP-PLAUSIOBEN',
      ' '          'BDC_OKCODE'                     '=QMLM',
      ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
      ' '          'PLMKB-STELLEN'                  w_car-stellen,
      ' '          'RQPAS-MASSEINHSW'               w_car-masseinhsw,
      ' '          'QFLTP-SOLLWERT'                 w_car-sollwert,
      ' '          'QFLTP-TOLERANZUN'               w_car-toleranzun,
      ' '          'QFLTP-TOLERANZOB'               w_car-toleranzob,
      ' '          'QFLTP-PLAUSIUNTE'               w_car-plausiunte,
      ' '          'QFLTP-PLAUSIOBEN'               w_car-plausioben.

    IF w_car-charact_id1 IS NOT INITIAL OR w_car-codegr9o IS NOT INITIAL OR
       w_car-code9o      IS NOT INITIAL OR w_car-codegr9u IS NOT INITIAL OR
       w_car-code9u      IS NOT INITIAL.

      IF w_car-stellen    IS NOT INITIAL OR w_car-masseinhsw IS NOT INITIAL OR
         w_car-sollwert   IS NOT INITIAL OR w_car-toleranzun IS NOT INITIAL OR
         w_car-toleranzun IS NOT INITIAL OR w_car-plausiunte IS NOT INITIAL OR
         w_car-plausioben IS NOT INITIAL.

        PERFORM zf_preenche_bdcdata USING:
         'X'          'SAPLQPAA'                       '0160',
         ' '          'BDC_CURSOR'                     'PLMKB-CODE9U',
         ' '          'BDC_OKCODE'                     '=QMBU',
         ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
         ' '          'PLMKB-KATALGART2'               w_car-katalgart2,
         ' '          'PLMKB-AUSWMENGE2'               w_car-auswmenge2,
         ' '          'PLMKB-AUSWMGWRK2'               w_car-auswmgwrk2,
         ' '          'PLMKB-CODEQUAL'                 w_car-codequal,
         ' '          'PLMKB-CODEGRQUAL'               w_car-codegrqual,
         ' '          'PLMKB-CODE9O'                   w_car-code9o,
         ' '          'PLMKB-CODEGR9O'                 w_car-codegr9o,
         ' '          'PLMKB-CODE9U'                   w_car-code9u,
         ' '          'PLMKB-CODEGR9U'                 w_car-codegr9u.


      ENDIF.
    ENDIF.

  ELSE.
    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-QERGDATH',
        ' '          'BDC_OKCODE'                     '=QMLM',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-PROBENR'                  w_car-probenr,
        ' '          'PLMKB-PRUEFQUALI'               w_car-pruefquali,
        ' '          'PLMKB-EEANTVERF'                w_car-eeantverf,
        ' '          'PLMKB-MERKGEW'                  w_car-merkgew,
        ' '          'PLMKB-CHARACT_ID1'              w_car-charact_id1,
        ' '          'PLMKB-QERGDATH'                 w_car-qergdath.

    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-CODEQUAL',
        ' '          'BDC_OKCODE'                     '=QMBU',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-KATALGART2'               w_car-katalgart2,
        ' '          'PLMKB-AUSWMENGE2'               w_car-auswmenge2,
        ' '          'PLMKB-AUSWMGWRK2'               w_car-auswmgwrk2,
        ' '          'PLMKB-CODEQUAL'                 w_car-codequal,
        ' '          'PLMKB-CODEGRQUAL'               w_car-codegrqual.
  ENDIF.

  CLEAR: l_flag.

ENDFORM.                    " ZF_MONTA_LISTA_TAREFAS_LOCAL_T
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_LISTA_TAREFAS_EQUIP_E
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_lista_tarefas_equip_e .
  DATA: l_data(8) TYPE c, "Formatar data
       l_flag   TYPE c.

  CLEAR: l_data, l_flag.

  TRANSLATE w_cab-profidnetz TO UPPER CASE.

* colocar data no formato dia mes ano
  CONCATENATE sy-datum+6(2) sy-datum+4(2) sy-datum+0(4) INTO l_data.

  PERFORM zf_preenche_bdcdata USING:
     'X'         'SAPLCPDI'             '3010',
     ' '         'BDC_CURSOR'           'RC271-PLNAL',
     ' '         'BDC_OKCODE'           '=VOUE',
     ' '         'RC27E-EQUNR'          v_plnnr,
     ' '         'RC271-PROFIDNETZ'     w_cab-profidnetz,
     ' '         'RC271-STTAG'          l_data,
     ' '         'RC271-PLNAL'          space.

  PERFORM zf_preenche_bdcdata USING:
    'X'         'SAPLCPDI'             '3400',
    ' '         'BDC_CURSOR'           'PLPOD-VORNR(01)',
    ' '         'BDC_OKCODE'           '=QMUE',
    ' '         'RC27X-FLG_SEL(01)'    c_x.

  PERFORM zf_preenche_bdcdata USING:
   'X'         'SAPLQPAA'             '0150',
   ' '         'BDC_CURSOR'           'PLMKB-MERKNR(01)',
   ' '         'BDC_OKCODE'           '=QMEF',
*     ' '         'RQPAS-ENTRY_ACT'      w_car-
   ' '         'RQPAS-SEL_FLG(01)'    c_x.

  PERFORM zf_preenche_bdcdata USING:
    'X'          'SAPLQPAA'                       '0150',
    ' '          'BDC_CURSOR'                     'PLMKB-DUMMY40(01)',
    ' '          'BDC_OKCODE'                     '=QMAM',
    ' '          'PLMKB-MERKNR(01)'               w_car-merknr,
    ' '          'PLMKB-VERWMERKM(01)'            w_car-verwmerkm,
    ' '          'PLMKB-QPMK_WERKS(01)'           w_car-qmtb_werks,
    ' '          'PLMKB-MKVERSION(01)'            w_car-mkversion,
    ' '          'PLMKB-KURZTEXT(01)'             w_car-kurztext,
    ' '          'PLMKB-PMETHODE(01)'             w_car-pmethode,
    ' '          'PLMKB-PMTVERSION(01)'           w_car-pmtversion,
    ' '          'PLMKB-STICHPRVER(01)'           w_car-stichprver,
    ' '          'PLMKB-DUMMY10(01)'              w_car-dummy10,
    ' '          'PLMKB-DUMMY20(01)'              w_car-dummy20,
    ' '          'PLMKB-DUMMY40(01)'              w_car-dummy40,
    ' '          'RQPAS-SEL_FLG(01)'              c_x.

  PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1501',
      ' '          'BDC_CURSOR'                     'PLMKB-VERWMERKM',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-VERWMERKM'                w_car-verwmerkm,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-MKVERSION'                w_car-mkversion.

  IF w_car-formel1 IS NOT INITIAL.
    PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '1522',
      ' '          'BDC_CURSOR'                     'PLMKB-FORMEL1',
      ' '          'BDC_OKCODE'                     '=ENT1',
      ' '          'PLMKB-FORMELSL'                 c_x," w_car-formelsl,
      ' '          'PLMKB-QPMK_WERKS'               w_car-qmtb_werks,
      ' '          'PLMKB-FORMEL1'                  w_car-formel1,
      ' '          'PLMKB-FORMEL2'                  w_car-formel2.
    l_flag = c_x.
  ENDIF.
  IF l_flag IS NOT INITIAL.
    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-QERGDATH',
        ' '          'BDC_OKCODE'                     '=QMNM',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-PROBENR'                  w_car-probenr,
        ' '          'PLMKB-PRUEFQUALI'               w_car-pruefquali,
        ' '          'PLMKB-EEANTVERF'                w_car-eeantverf,
        ' '          'PLMKB-MERKGEW'                  w_car-merkgew,
        ' '          'PLMKB-QERGDATH'                 w_car-qergdath.

    PERFORM zf_preenche_bdcdata USING:
      'X'          'SAPLQPAA'                       '0160',
      ' '          'BDC_CURSOR'                     'QFLTP-PLAUSIOBEN',
      ' '          'BDC_OKCODE'                     '=QMLM',
      ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
      ' '          'PLMKB-STELLEN'                  w_car-stellen,
      ' '          'RQPAS-MASSEINHSW'               w_car-masseinhsw,
      ' '          'QFLTP-SOLLWERT'                 w_car-sollwert,
      ' '          'QFLTP-TOLERANZUN'               w_car-toleranzun,
      ' '          'QFLTP-TOLERANZOB'               w_car-toleranzob,
      ' '          'QFLTP-PLAUSIUNTE'               w_car-plausiunte,
      ' '          'QFLTP-PLAUSIOBEN'               w_car-plausioben.

    IF w_car-charact_id1 IS NOT INITIAL OR w_car-codegr9o IS NOT INITIAL OR
       w_car-code9o      IS NOT INITIAL OR w_car-codegr9u IS NOT INITIAL OR
       w_car-code9u      IS NOT INITIAL.

      IF w_car-stellen    IS NOT INITIAL OR w_car-masseinhsw IS NOT INITIAL OR
         w_car-sollwert   IS NOT INITIAL OR w_car-toleranzun IS NOT INITIAL OR
         w_car-toleranzun IS NOT INITIAL OR w_car-plausiunte IS NOT INITIAL OR
         w_car-plausioben IS NOT INITIAL.

        PERFORM zf_preenche_bdcdata USING:
         'X'          'SAPLQPAA'                       '0160',
         ' '          'BDC_CURSOR'                     'PLMKB-CODE9U',
         ' '          'BDC_OKCODE'                     '=QMBU',
         ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
         ' '          'PLMKB-KATALGART2'               w_car-katalgart2,
         ' '          'PLMKB-AUSWMENGE2'               w_car-auswmenge2,
         ' '          'PLMKB-AUSWMGWRK2'               w_car-auswmgwrk2,
         ' '          'PLMKB-CODEQUAL'                 w_car-codequal,
         ' '          'PLMKB-CODEGRQUAL'               w_car-codegrqual,
         ' '          'PLMKB-CODE9O'                   w_car-code9o,
         ' '          'PLMKB-CODEGR9O'                 w_car-codegr9o,
         ' '          'PLMKB-CODE9U'                   w_car-code9u,
         ' '          'PLMKB-CODEGR9U'                 w_car-codegr9u.


      ENDIF.
    ENDIF.

  ELSE.
    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-QERGDATH',
        ' '          'BDC_OKCODE'                     '=QMLM',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-PROBENR'                  w_car-probenr,
        ' '          'PLMKB-PRUEFQUALI'               w_car-pruefquali,
        ' '          'PLMKB-EEANTVERF'                w_car-eeantverf,
        ' '          'PLMKB-MERKGEW'                  w_car-merkgew,
        ' '          'PLMKB-CHARACT_ID1'              w_car-charact_id1,
        ' '          'PLMKB-QERGDATH'                 w_car-qergdath.

    PERFORM zf_preenche_bdcdata USING:
        'X'          'SAPLQPAA'                       '0160',
        ' '          'BDC_CURSOR'                     'PLMKB-CODEQUAL',
        ' '          'BDC_OKCODE'                     '=QMBU',
        ' '          'PLMKB-KURZTEXT'                 w_car-kurztext,
        ' '          'PLMKB-KATALGART2'               w_car-katalgart2,
        ' '          'PLMKB-AUSWMENGE2'               w_car-auswmenge2,
        ' '          'PLMKB-AUSWMGWRK2'               w_car-auswmgwrk2,
        ' '          'PLMKB-CODEQUAL'                 w_car-codequal,
        ' '          'PLMKB-CODEGRQUAL'               w_car-codegrqual.
  ENDIF.

  CLEAR: l_flag.

ENDFORM.                    " ZF_MONTA_LISTA_TAREFAS_EQUIP_E
*&---------------------------------------------------------------------*
*&      Form  ZF_CHAMA_TRANSACTION
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*      -->P_C_IA06  text
*      -->P_V_MODO  text
*      -->P_C_S  text
*----------------------------------------------------------------------*
FORM zf_chama_transaction  USING      value(p_trans)  TYPE c
                                      value(p_modo)   TYPE c
                                      value(p_update) TYPE c.

  DATA: l_msg_text(100) TYPE c. "Mensagens da transação

*  p_modo = 'A'.
* Executa a transação
  CALL TRANSACTION p_trans USING    t_bdc
                           MODE     p_modo
                           UPDATE   p_update
                           MESSAGES INTO t_messtab.

  CLEAR t_bdc.
  REFRESH t_bdc.

ENDFORM.                    " ZF_CHAMA_TRANSACTION
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_LOG_BAPI
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_log_bapi .
  LOOP AT t_return_cre INTO w_return_cre.
    w_log-plnnr = w_cab-plnnr.
    w_log-messg = w_return_cre-message.
    APPEND w_log TO t_log.
    CLEAR: w_log, w_return_cre.
  ENDLOOP.
  REFRESH t_return_cre.
ENDFORM.                    " ZF_MONTA_LOG_BAPI
*&---------------------------------------------------------------------*
*&      Form  ZF_WRITE_LOG
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_write_log .
  WRITE: text-t07, text-t08.

  LOOP AT t_log INTO w_log.

    WRITE: w_log-plnnr, w_log-messg.

  ENDLOOP.

ENDFORM.                    " ZF_WRITE_LOG
*&---------------------------------------------------------------------*
*&      Form  ZF_TEXTO_LONGO
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_texto_longo .

  DATA: l_plnnr             TYPE plpo-plnnr,
        l_tabix             TYPE sy-tabix,
        l_plnty(1)          TYPE c.


*descobrindo operação e sub-operação
  IF NOT t_text[] IS INITIAL.
    REFRESH: t_plpo[].
    SELECT plnty plnnr plnkn zaehl sumnr vornr
    FROM plpo
    INTO TABLE t_plpo
    FOR ALL ENTRIES IN t_text
    WHERE
*plnty = v_plnty "'E' AND
      plnnr = t_text-plnnr
      AND sumnr = '00000000'.
  ENDIF.

  IF NOT t_plpo[] IS INITIAL.
*Descobre suboperação
    REFRESH: t_sub[].
    SELECT plnty plnnr plnkn zaehl sumnr vornr
    FROM plpo
    INTO TABLE t_sub
    FOR ALL ENTRIES IN t_plpo
    WHERE
*      plnty = v_plnty "'E' AND
       plnnr = t_plpo-plnnr
      AND sumnr = t_plpo-plnkn.
  ENDIF.

  DATA l_velho TYPE plpo-plnnr.
  SORT t_text BY plnnr.


  IF v_flag IS INITIAL. " Texto longo e outros selecionados.

    LOOP AT t_aux INTO w_aux.

      READ TABLE t_text INTO w_text WITH KEY plnnr = w_aux-plnnr.
      IF sy-subrc = 0.
        l_velho = w_text-plnnr.
        l_tabix = sy-tabix.
        LOOP AT t_text INTO w_text FROM l_tabix.
          IF w_text-plnnr NE l_velho.
            EXIT.
          ENDIF.
          l_velho = w_text-plnnr.


          IF w_aux-plnnr_new IS  INITIAL.
            l_plnnr = w_aux-plnnr.
          ELSE.
            l_plnnr = w_aux-plnnr_new.
          ENDIF.


          IF w_text-vornr IS  INITIAL.

            CONCATENATE sy-mandt w_aux-plnty l_plnnr '1' INTO w_header-tdname.
            CONCATENATE w_header-tdname '00000001' INTO w_header-tdname SEPARATED BY space.

            w_header-tdobject                      = 'ROUTING'.
            w_header-tdname                        = w_header-tdname. "'182E000048980100000001'.
            w_header-tdid                          = 'PLKO'.
            w_header-tdform                        = 'SYSTEM'.
            w_header-tdspras                       = sy-langu.
            w_header-tdospras                      = sy-langu.

          ELSEIF NOT w_text-vornr IS INITIAL.

            READ TABLE t_plpo INTO w_plpo WITH KEY plnnr = w_text-plnnr
                                                   vornr = w_text-vornr
                                                   sumnr = '00000000'.
            IF sy-subrc IS INITIAL.
              IF NOT w_text-uvorn IS INITIAL.
                READ TABLE t_sub INTO w_sub WITH KEY plnnr = w_text-plnnr
                                                     vornr = w_text-uvorn
                                                     sumnr = w_plpo-plnkn.
                IF sy-subrc IS INITIAL.
                  CONCATENATE sy-mandt w_aux-plnty l_plnnr '01' w_sub-plnkn INTO w_header-tdname.
                ENDIF.
              ELSE.
                CONCATENATE sy-mandt w_aux-plnty l_plnnr '01' w_plpo-plnkn INTO w_header-tdname.
              ENDIF.
            ENDIF.

            w_header-tdobject                      = 'ROUTING'.
            w_header-tdname                        = w_header-tdname. "'182E000048980100000001'.
            w_header-tdid                          = 'PLPO'.
            w_header-tdspras                       = sy-langu.
          ENDIF.

*chama save_text
* Função que grava texto longo
          PERFORM zf_chama_save_text USING l_plnnr.
        ENDLOOP.
      ENDIF.
    ENDLOOP.
  ENDIF.

**********************************************************************
  " Arquivo somente o txt selecionado.
**********************************************************************

  IF v_flag = c_x.
    LOOP AT t_cab INTO w_cab.

      READ TABLE t_text INTO w_text WITH KEY plnnr = w_cab-plnnr.
      IF sy-subrc IS INITIAL.
        l_velho = w_text-plnnr.
        l_tabix = sy-tabix.
        LOOP AT t_text INTO w_text FROM l_tabix.
          IF w_text-plnnr NE l_velho.
            EXIT.
          ENDIF.
          l_velho = w_text-plnnr.

          IF w_cab-equnr IS INITIAL AND w_cab-tplnr IS INITIAL.
            l_plnty = c_a.
          ELSEIF NOT w_cab-equnr IS INITIAL AND  w_cab-tplnr IS INITIAL.
            l_plnty = c_e.
          ELSEIF w_cab-equnr IS INITIAL AND NOT w_cab-tplnr IS INITIAL.
            l_plnty = c_t.
          ELSE.
          ENDIF.



          IF w_text-vornr IS  INITIAL.

            CONCATENATE sy-mandt l_plnty w_cab-plnnr '1' INTO w_header-tdname.
            CONCATENATE w_header-tdname '00000001' INTO w_header-tdname SEPARATED BY space.


            w_header-tdobject                      = 'ROUTING'.
            w_header-tdname                        = w_header-tdname. "'182E000048980100000001'.
            w_header-tdid                          = 'PLKO'.
            w_header-tdspras                       = sy-langu.

          ELSEIF NOT w_text-vornr IS INITIAL.

            READ TABLE t_plpo INTO w_plpo WITH KEY plnnr = w_text-plnnr
                                                   vornr = w_text-vornr
                                                   sumnr = '00000000'.
            IF sy-subrc IS INITIAL.
              IF NOT w_text-uvorn IS INITIAL.
                READ TABLE t_sub INTO w_sub WITH KEY plnnr = w_text-plnnr
                                                     vornr = w_text-uvorn
                                                     sumnr = w_plpo-plnkn.
                IF sy-subrc IS INITIAL.
                  CONCATENATE sy-mandt l_plnty w_text-plnnr w_sub-plnkn w_sub-plnkn INTO w_header-tdname.
                ENDIF.
              ELSE.
                CONCATENATE sy-mandt l_plnty w_text-plnnr w_plpo-plnkn w_plpo-plnkn INTO w_header-tdname.
              ENDIF.
            ENDIF.
            w_header-tdobject                      = 'ROUTING'.
            w_header-tdname                        = w_header-tdname. "'182E000048980100000001'.
            w_header-tdid                          = 'PLPO'.
            w_header-tdspras                       = sy-langu.

          ENDIF.

          PERFORM zf_chama_save_text USING w_text-plnnr.
        ENDLOOP.
      ENDIF.
    ENDLOOP.
  ENDIF.


ENDFORM.                    " ZF_TEXTO_LONGO
*&---------------------------------------------------------------------*
*&      Form  ZF_SALVA_NOVO_PLNNR
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_salva_novo_plnnr .

  w_aux-plnnr = w_cab-plnnr.
  w_aux-plnty = v_plnty.
  w_aux-plnnr_new = v_plnnr .
  APPEND w_aux TO t_aux.
  CLEAR w_aux.

ENDFORM.                    " ZF_SALVA_NOVO_PLNNR
*&---------------------------------------------------------------------*
*&      Form  ZF_MONTA_TEXTO
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_monta_texto .
  DATA l_linha(8) TYPE c.

  CALL FUNCTION 'IMPORT_TEXT'
    EXPORTING
      codepage        = '1100'
      file            = w_text-caminho
      format_type     = 'ASCII'
      header          = w_header
      mask_brackets   = 'X'
    TABLES
      itf_lines       = t_lines
    EXCEPTIONS
      file_open_error = 1
      file_read_error = 2
      upload_error    = 3
      no_contents     = 4
      OTHERS          = 5.

* quantidade de linhas
  DESCRIBE TABLE t_lines LINES l_linha.
  CONDENSE l_linha.

  CALL FUNCTION 'CONVERSION_EXIT_ALPHA_INPUT'
    EXPORTING
      input  = l_linha
    IMPORTING
      output = l_linha.

  w_text_bapi-plnty = w_cab_bapi-plnty.
  w_text_bapi-langu = sy-langu.
  w_text_bapi-langu_iso = sy-langu.
  w_text_bapi-textstart = '00000001'.
  w_text_bapi-textend   = l_linha.
  APPEND w_text_bapi TO t_text_bapi.

  LOOP AT t_lines INTO w_lines.

    IF sy-tabix = 1.
      w_l_bapi-tdformat = '*'.
      w_l_bapi-tdline = w_cab_bapi-ktext.
      APPEND w_l_bapi TO t_text_l_bapi.
    ELSE.

      w_l_bapi-tdformat = w_lines-tdformat.
      w_l_bapi-tdline   = w_lines-tdline.
      APPEND w_l_bapi TO t_text_l_bapi.
      CLEAR w_l_bapi.

    ENDIF.

  ENDLOOP.

ENDFORM.                    " ZF_MONTA_TEXTO
*&---------------------------------------------------------------------*
*&      Form  ZF_CHAMA_SAVE_TEXT
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_chama_save_text USING p_plnnr TYPE plpo-plnnr.

  DATA: l_count             LIKE sy-index.

  CALL FUNCTION 'IMPORT_TEXT'
    EXPORTING
      codepage        = '1100'
      file            = w_text-caminho "'C:\Users\nmantovi\Desktop\campos_faltantes_felipe.txt' "
      format_type     = 'ASCII'
      header          = w_header
      mask_brackets   = 'X'
    TABLES
      itf_lines       = t_lines
    EXCEPTIONS
      file_open_error = 1
      file_read_error = 2
      upload_error    = 3
      no_contents     = 4
      OTHERS          = 5.


  CALL FUNCTION 'SAVE_TEXT'
    EXPORTING
      client          = sy-mandt
      header          = w_header
      savemode_direct = c_x
    TABLES
      lines           = t_lines
    EXCEPTIONS
      id              = 1
      language        = 2
      name            = 3
      object          = 4
      OTHERS          = 5.

  IF sy-subrc = 0.

    CALL FUNCTION 'COMMIT_TEXT'
      EXPORTING
        object          = w_header-tdobject
        name            = w_header-tdname
        id              = w_header-tdid
        language        = w_header-tdspras
        savemode_direct = 'X'
      IMPORTING
        commit_count    = l_count.


    IF sy-subrc = 0.

      IF sy-subrc = 0.
        w_log-plnnr = p_plnnr.
        w_log-messg = text-t09.
        APPEND w_log TO t_log.
        CLEAR w_log.
      ELSE.
        w_log-plnnr = p_plnnr.
        w_log-messg = text-t10.
        APPEND w_log TO t_log.
        CLEAR w_log.
      ENDIF.

    ENDIF.
  ENDIF.

ENDFORM.                    " ZF_CHAMA_SAVE_TEXT
*&---------------------------------------------------------------------*
*&      Form  ZF_CARREGA_CAMPO_TDNAME
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
FORM zf_carrega_campo_tdname USING p_plnnr TYPE plpo-plnnr.

  IF w_aux-plnty = c_a.

    CONCATENATE sy-mandt w_aux-plnty p_plnnr '1' INTO w_header-tdname.
    CONCATENATE w_header-tdname '00000001' INTO w_header-tdname SEPARATED BY space.

  ELSEIF w_aux-plnty = c_e.

    CONCATENATE sy-mandt w_aux-plnty p_plnnr '01' '00000001' INTO w_header-tdname.

  ELSEIF w_aux-plnty = c_t.

    CONCATENATE sy-mandt w_aux-plnty p_plnnr '01' '00000001' INTO w_header-tdname.

  ENDIF.


ENDFORM.                    " ZF_CARREGA_CAMPO_TDNAME

