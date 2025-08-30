```mermaid
graph TD
    denuncia[Denúncia]

    no_req[Não preenchidos os requisitos legais.]:::red
    sem_just[Sem justificativa para não oferta de benefícios]:::red
    just_oferta[Justificada a não oferta de benefícios despenalizadores e preenchidos os requisitos legais <br>(qualificação, narrativa, imputação, rol de testemunhas).]
    oferta_susp[Oferecida Suspensão condicional do processo]

    admiss[Admissibilidade do recurso <br>(modelo 1000306340)]:::green
    rejeitar[Rejeitar <br>(modelo )]:::green
    intimar_mp[Intimar MP para justificar <br>(modelo )]
    recebimento[Recebimento <br>(modelo 1000666740)]:::green
    design_aud_scp[Designar audiência para oferta da SCP <br>(modelo )]:::green
    term_aud_scp[TERM DE AUDIÊNCIA <br>(modelo )]

    verificar_dil[Verificar se há pedido de diligências]
    expedir_mand[Expedir mandado de citação]
    cump_neg[Cumprimento negativo <br>Localização da tentativa de localização do réu]:::red
    cump_pos[Cumprimento positivo <br>Citação pessoal do réu]
    det_cit_edital[Determinar citação por edital <br>(modelo 1000131724)]:::green
    reu_nao_comp[Réu não comparece]:::red
    reu_comp[Réu comparece]
    susp_366[Suspensão Art. 366 <br>(modelo 1000273404)]:::red
    oferece_resp[Oferece resposta à acusação]
    absol_sum[Absolvição sumária]
    design_aud_ij[Designar audiência de instrução e julgamento <br>(modelo 1000147288)]:::green
    term_aud_ij[TERM DE AUDIÊNCIA <br>(modelo 1000605373)]
    term_aud_dir[TERM DE AUDIÊNCIA <br>(modelo )]

    denuncia --> no_req
    denuncia --> sem_just
    denuncia --> just_oferta
    denuncia --> oferta_susp

    no_req --> admiss
    admiss --> rejeitar

    sem_just --> intimar_mp

    just_oferta --> recebimento

    oferta_susp --> design_aud_scp
    design_aud_scp --> term_aud_scp

    recebimento --> verificar_dil
    verificar_dil -- Sim --> expedir_mand
    verificar_dil -- Não --> term_aud_dir

    expedir_mand --> cump_neg
    expedir_mand --> cump_pos

    cump_neg --> det_cit_edital
    det_cit_edital --> reu_nao_comp
    det_cit_edital --> reu_comp

    reu_nao_comp --> susp_366

    reu_comp --> oferece_resp
    cump_pos --> oferece_resp

    oferece_resp --> absol_sum
    oferece_resp --> design_aud_ij
    design_aud_ij --> term_aud_ij

    classDef red fill:#ffdddd, stroke:#ff0000, stroke-width:2px, color:#000;
    classDef green fill:#ddffdd, stroke:#00aa00, stroke-width:2px, color:#000;
