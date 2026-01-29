<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>GYM TRACK • HS</title>

  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg:#070A0F;
      --panel:#0B1220;
      --panel2:#0E1A30;
      --text:#EAF2FF;
      --muted:#94A3B8;
      --line:rgba(148,163,184,.18);
      --neon:#00F5FF;
      --lime:#A6FF00;
      --warn:#FFB020;
      --bad:#FF4D6D;
      --ok:#2BFF88;
      --shadow: 0 18px 60px rgba(0,0,0,.55);
      --radius: 18px;
    }
    *{box-sizing:border-box}
    body{
      margin:0; font-family:Inter,system-ui,Arial; color:var(--text);
      background:
        radial-gradient(1200px 600px at 20% 10%, rgba(0,245,255,.18), transparent 60%),
        radial-gradient(900px 500px at 85% 20%, rgba(166,255,0,.12), transparent 55%),
        radial-gradient(700px 600px at 60% 80%, rgba(255,77,109,.10), transparent 60%),
        var(--bg);
      min-height:100vh;
    }
    .wrap{max-width:1180px; margin:0 auto; padding:22px 16px 44px;}
    .topbar{display:flex; align-items:center; justify-content:space-between; gap:12px; margin-bottom:16px;}
    .brand{
      display:flex; align-items:center; gap:10px;
      padding:10px 14px; border:1px solid var(--line);
      border-radius:999px; background:rgba(255,255,255,.03);
      box-shadow: var(--shadow); backdrop-filter: blur(10px);
    }
    .brand .logo{
      width:34px; height:34px; border-radius:12px;
      background: linear-gradient(135deg, var(--neon), var(--lime));
      display:grid; place-items:center; color:#061019; font-weight:900;
    }
    .brand .title{font-weight:800; letter-spacing:.4px}
    .pill{
      display:flex; gap:10px; align-items:center;
      padding:10px 12px; border-radius:999px;
      border:1px solid var(--line); background:rgba(255,255,255,.03);
    }
    .pill small{color:var(--muted)}
    .btn{
      border:0; cursor:pointer; color:var(--text);
      background:rgba(255,255,255,.06); border:1px solid var(--line);
      padding:10px 12px; border-radius:12px;
      display:inline-flex; align-items:center; gap:8px;
      transition:.15s;
    }
    .btn:hover{transform:translateY(-1px); background:rgba(255,255,255,.09)}
    .btn.primary{
      border-color: rgba(0,245,255,.35);
      background: linear-gradient(135deg, rgba(0,245,255,.18), rgba(166,255,0,.10));
    }
    .btn.danger{
      border-color: rgba(255,77,109,.35);
      background: rgba(255,77,109,.08);
    }
    .btn.ok{
      border-color: rgba(43,255,136,.35);
      background: rgba(43,255,136,.08);
    }

    .grid{display:grid; gap:14px; grid-template-columns: 1.1fr .9fr;}
    @media (max-width: 980px){ .grid{grid-template-columns: 1fr;} }

    .card{
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.02));
      border:1px solid var(--line);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      backdrop-filter: blur(10px);
      overflow:hidden;
    }
    .card .hd{
      padding:16px 16px 10px;
      border-bottom:1px solid var(--line);
      display:flex; align-items:flex-start; justify-content:space-between; gap:10px;
    }
    .card .hd h2{margin:0; font-size:16px; font-weight:800; letter-spacing:.2px}
    .card .hd p{margin:6px 0 0; color:var(--muted); font-size:12px}
    .card .bd{padding:16px}

    .row{display:grid; grid-template-columns:1fr 1fr; gap:12px}
    @media (max-width: 640px){ .row{grid-template-columns:1fr;} }

    label{display:block; font-size:12px; color:var(--muted); margin:0 0 6px}
    input, select, textarea{
      width:100%; padding:12px 12px;
      background: rgba(0,0,0,.25);
      border:1px solid var(--line);
      border-radius:12px; color:var(--text);
      outline:none;
    }
    textarea{min-height:90px; resize:vertical}
    .hint{color:var(--muted); font-size:12px; margin-top:8px}
    .tabs{display:flex; gap:10px; flex-wrap:wrap; margin:12px 0 0;}
    .tab{
      padding:10px 12px; border-radius:999px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.04);
      cursor:pointer; user-select:none;
      display:flex; gap:8px; align-items:center;
      font-size:13px;
    }
    .tab.active{
      border-color: rgba(0,245,255,.35);
      background: rgba(0,245,255,.10);
    }

    .kpis{display:grid; gap:12px; grid-template-columns: repeat(3, 1fr);}
    @media (max-width: 780px){ .kpis{grid-template-columns:1fr;} }
    .kpi{
      padding:14px; border-radius:16px;
      border:1px solid var(--line);
      background: rgba(0,0,0,.18);
    }
    .kpi .lbl{color:var(--muted); font-size:12px}
    .kpi .val{font-weight:900; font-size:22px; margin-top:6px}
    .kpi .sub{color:var(--muted); font-size:12px; margin-top:6px}

    .badge{
      display:inline-flex; align-items:center; gap:8px;
      padding:8px 10px; border-radius:999px;
      border:1px solid var(--line);
      background: rgba(0,0,0,.20);
      font-size:12px; color:var(--muted);
    }

    .banner{
      padding:12px 12px;
      border-radius:16px;
      border:1px solid rgba(255,176,32,.35);
      background: rgba(255,176,32,.08);
      display:flex; align-items:flex-start; gap:10px;
    }
    .banner.ok{border-color: rgba(43,255,136,.35); background: rgba(43,255,136,.08);}
    .banner.bad{border-color: rgba(255,77,109,.35); background: rgba(255,77,109,.08);}
    .sep{height:1px; background:var(--line); margin:14px 0}

    .list{
      border:1px solid var(--line); border-radius:16px; overflow:hidden;
      background: rgba(0,0,0,.18);
    }
    .list .it{
      padding:12px 12px; border-bottom:1px solid var(--line);
      display:flex; justify-content:space-between; gap:10px; align-items:center;
      font-size:13px;
    }
    .list .it:last-child{border-bottom:0}
    .muted{color:var(--muted)}
    .hidden{display:none !important}
    .right{display:flex; gap:10px; align-items:center}
    .chip{
      font-size:12px; padding:6px 10px; border-radius:999px;
      border:1px solid var(--line); color:var(--muted);
      background: rgba(255,255,255,.03);
      white-space:nowrap;
    }
    .chip.ok{border-color: rgba(43,255,136,.35); color:rgba(43,255,136,.95); background: rgba(43,255,136,.06);}
    .chip.warn{border-color: rgba(255,176,32,.35); color:rgba(255,176,32,.95); background: rgba(255,176,32,.06);}
    .chip.bad{border-color: rgba(255,77,109,.35); color:rgba(255,77,109,.95); background: rgba(255,77,109,.06);}

    .progress{
      width:100%; height:10px; border-radius:999px;
      background: rgba(255,255,255,.08); border:1px solid var(--line);
      overflow:hidden;
    }
    .progress > div{
      height:100%;
      background: linear-gradient(135deg, rgba(0,245,255,.85), rgba(166,255,0,.75));
      width:0%;
      transition: width .25s;
    }

    .twoCol{display:grid; grid-template-columns:1fr 1fr; gap:12px}
    @media (max-width: 820px){ .twoCol{grid-template-columns:1fr;} }

    .timerBox{
      display:flex; gap:10px; align-items:center; flex-wrap:wrap;
    }
    .bigTime{
      font-size:28px; font-weight:900; letter-spacing:.5px;
      padding:10px 12px; border-radius:14px;
      border:1px solid var(--line); background: rgba(0,0,0,.20);
    }

    .footerNote{margin-top:14px; color:var(--muted); font-size:12px}
  </style>
</head>

<body>
  <div class="wrap">
    <div class="topbar">
      <div class="brand">
        <div class="logo"><i class="fa-solid fa-dumbbell"></i></div>
        <div>
          <div class="title">GYM TRACK</div>
          <small class="muted">Treinos • Mensalidade • Progresso</small>
        </div>
      </div>

      <div class="pill">
        <small id="sessionInfo">Não autenticado</small>
        <button class="btn" id="btnLogout" onclick="logout()" style="display:none">
          <i class="fa-solid fa-right-from-bracket"></i> Sair
        </button>
      </div>
    </div>

    <!-- LOGIN -->
    <div class="grid" id="viewLogin">
      <div class="card">
        <div class="hd">
          <div>
            <h2>Entrar</h2>
            <p>Escolha o tipo de acesso e entre com seus dados.</p>
          </div>
          <span class="badge"><i class="fa-solid fa-bolt"></i> Vibe Academia</span>
        </div>
        <div class="bd">
          <div class="tabs">
            <div class="tab active" id="tabUser" onclick="setLoginMode('user')"><i class="fa-solid fa-user"></i> Usuário</div>
            <div class="tab" id="tabMaster" onclick="setLoginMode('master')"><i class="fa-solid fa-user-shield"></i> Master</div>
          </div>

          <div class="sep"></div>

          <div class="row">
            <div>
              <label>Usuário (login)</label>
              <input id="loginUser" placeholder="ex: will" autocomplete="username">
            </div>
            <div>
              <label>Senha</label>
              <input id="loginPass" type="password" placeholder="••••••••" autocomplete="current-password">
            </div>
          </div>

          <div class="hint" id="loginHint">
            Usuário: entra para ver treinos e avisos de mensalidade.
          </div>

          <div class="sep"></div>

          <button class="btn primary" onclick="doLogin()">
            <i class="fa-solid fa-arrow-right-to-bracket"></i> Entrar
          </button>

          <div class="footerNote" id="loginMsg"></div>
        </div>
      </div>

      <div class="card">
        <div class="hd">
          <div>
            <h2>Extras implementados</h2>
            <p>Streak, meta semanal, timer, PR, check-in, recados e inatividade.</p>
          </div>
        </div>
        <div class="bd">
          <div class="banner ok">
            <i class="fa-solid fa-lock"></i>
            <div>
              <div style="font-weight:800">Master protegido (servidor)</div>
              <div class="muted" style="font-size:12px;margin-top:4px">
                Senha do master não fica fixa no front — valida no Apps Script e devolve token.
              </div>
            </div>
          </div>

          <div class="sep"></div>

          <div class="muted" style="font-size:13px; line-height:1.6">
            • Aviso de mensalidade faltando 7 dias (todo dia no painel).<br>
            • Checkbox “Concluí” avança o treino e alimenta streak/meta.<br>
            • Timer de descanso com presets (1/2/3 min).<br>
            • Registro de PR/carga por exercício.<br>
            • Check-in diário (presença).<br>
            • Alerta de inatividade e recados do Master.
          </div>
        </div>
      </div>
    </div>

    <!-- MASTER -->
    <div class="grid hidden" id="viewMaster">
      <div class="card">
        <div class="hd">
          <div>
            <h2>Painel Master</h2>
            <p>Usuários, mensalidades e controle geral.</p>
          </div>
          <span class="badge"><i class="fa-solid fa-chart-simple"></i> KPIs</span>
        </div>
        <div class="bd">
          <div class="kpis">
            <div class="kpi">
              <div class="lbl">Usuários (Total)</div>
              <div class="val" id="kpiTotal">—</div>
              <div class="sub">cadastros no banco</div>
            </div>
            <div class="kpi">
              <div class="lbl">Usuários Ativos</div>
              <div class="val" id="kpiAtivos">—</div>
              <div class="sub">status = ATIVO</div>
            </div>
            <div class="kpi">
              <div class="lbl">Receita (Ativos)</div>
              <div class="val" id="kpiReceita">—</div>
              <div class="sub">mensalidades ativas</div>
            </div>
          </div>

          <div class="sep"></div>

          <div class="twoCol">
            <div>
              <div class="banner" id="dueBox" style="align-items:center">
                <i class="fa-solid fa-triangle-exclamation"></i>
                <div>
                  <div style="font-weight:800">Vencendo em até 7 dias</div>
                  <div class="muted" style="font-size:12px;margin-top:4px" id="dueCount">—</div>
                </div>
              </div>
            </div>
            <div>
              <div class="banner bad" id="inactiveBox" style="align-items:center">
                <i class="fa-solid fa-user-slash"></i>
                <div>
                  <div style="font-weight:800">Inativos / sem treino</div>
                  <div class="muted" style="font-size:12px;margin-top:4px" id="inactiveCount">—</div>
                </div>
              </div>
            </div>
          </div>

          <div class="sep"></div>
          <button class="btn" onclick="refreshMaster()"><i class="fa-solid fa-rotate"></i> Atualizar KPIs</button>

          <div class="footerNote" id="masterMsg"></div>
        </div>
      </div>

      <div class="card">
        <div class="hd">
          <div>
            <h2>Cadastrar / Atualizar Usuário</h2>
            <p>Cria aba do cliente, define treino, vencimento, metas e status.</p>
          </div>
        </div>
        <div class="bd">
          <div class="row">
            <div>
              <label>Login do usuário</label>
              <input id="m_user" placeholder="ex: joao">
            </div>
            <div>
              <label>Senha do usuário</label>
              <input id="m_pass" placeholder="ex: 1234" type="password">
            </div>
          </div>

          <div class="row" style="margin-top:12px">
            <div>
              <label>Módulo de Treino</label>
              <select id="m_mod">
                <option value="A">A</option>
                <option value="B">B</option>
                <option value="C">C</option>
                <option value="ABCD">ABCD</option>
                <option value="CUSTOM">Custom</option>
              </select>
            </div>
            <div>
              <label>Se CUSTOM, nome do módulo</label>
              <input id="m_mod_custom" placeholder="ex: PUSH/PULL/LEGS">
            </div>
          </div>

          <div style="margin-top:12px">
            <label>Agrupamentos e sequência (um por linha)</label>
            <textarea id="m_seq" placeholder="ex:
A: Peito + Tríceps
B: Costas + Bíceps
C: Perna + Ombro"></textarea>
            <div class="hint">O sistema usa essa lista para continuar de onde parou (índice atual).</div>
          </div>

          <div class="row" style="margin-top:12px">
            <div>
              <label>Vencimento da mensalidade</label>
              <input id="m_due" type="date">
            </div>
            <div>
              <label>Status</label>
              <select id="m_status">
                <option value="ATIVO">ATIVO</option>
                <option value="INATIVO">INATIVO</option>
              </select>
            </div>
          </div>

          <div class="row" style="margin-top:12px">
            <div>
              <label>Valor da mensalidade (R$)</label>
              <input id="m_valor" inputmode="decimal" placeholder="ex: 120">
            </div>
            <div>
              <label>Pagamento (Master marca)</label>
              <select id="m_pago">
                <option value="NAO">NÃO</option>
                <option value="SIM">SIM</option>
              </select>
            </div>
          </div>

          <div class="row" style="margin-top:12px">
            <div>
              <label>Meta semanal (treinos por semana)</label>
              <input id="m_goal" inputmode="numeric" placeholder="ex: 4">
            </div>
            <div>
              <label>Dias para alertar inatividade</label>
              <input id="m_inact_days" inputmode="numeric" placeholder="ex: 7">
            </div>
          </div>

          <div class="sep"></div>

          <div class="right">
            <button class="btn primary" onclick="saveUserMaster()"><i class="fa-solid fa-floppy-disk"></i> Salvar</button>
            <button class="btn" onclick="loadUserMaster()"><i class="fa-solid fa-magnifying-glass"></i> Buscar</button>
          </div>

          <div class="sep"></div>

          <div class="row">
            <div>
              <label>Enviar recado para usuário</label>
              <input id="m_msg_user" placeholder="login do usuário">
            </div>
            <div>
              <label>Mensagem</label>
              <input id="m_msg_text" placeholder="ex: Lembra de alongar hoje!">
            </div>
          </div>
          <button class="btn ok" onclick="sendMasterMessage()"><i class="fa-solid fa-paper-plane"></i> Enviar recado</button>

          <div class="footerNote" id="masterMsg2"></div>
        </div>
      </div>
    </div>

    <!-- USUÁRIO -->
    <div class="grid hidden" id="viewUser">
      <div class="card">
        <div class="hd">
          <div>
            <h2 id="uTitle">Bem-vindo</h2>
            <p id="uSub">Seu treino e seu ritmo.</p>
          </div>
          <span class="badge"><i class="fa-solid fa-fire"></i> Consistência</span>
        </div>
        <div class="bd">
          <div id="uBillingBanner" class="banner hidden">
            <i class="fa-solid fa-triangle-exclamation"></i>
            <div>
              <div style="font-weight:800">Mensalidade perto do vencimento</div>
              <div class="muted" id="uBillingText" style="font-size:12px;margin-top:4px"></div>
            </div>
          </div>

          <div id="uInactiveBanner" class="banner bad hidden" style="margin-top:12px">
            <i class="fa-solid fa-user-slash"></i>
            <div>
              <div style="font-weight:800">Alerta de inatividade</div>
              <div class="muted" id="uInactiveText" style="font-size:12px;margin-top:4px"></div>
            </div>
          </div>

          <div class="sep"></div>

          <div class="twoCol">
            <div class="list">
              <div class="it">
                <div>
                  <div style="font-weight:800">Treino atual</div>
                  <div class="muted" id="uWorkout" style="font-size:12px;margin-top:4px">—</div>
                </div>
                <div class="right">
                  <span class="chip" id="uMod">—</span>
                </div>
              </div>

              <div class="it">
                <div>
                  <div style="font-weight:800">Você concluiu o último treino?</div>
                  <div class="muted" style="font-size:12px;margin-top:4px">
                    Marque e o sistema avança para o próximo (conta na meta e no streak).
                  </div>
                </div>
                <div class="right">
                  <input id="uDone" type="checkbox" style="width:22px;height:22px" onchange="markWorkoutDone()">
                </div>
              </div>

              <div class="it">
                <div>
                  <div style="font-weight:800">Check-in do dia</div>
                  <div class="muted" style="font-size:12px;margin-top:4px">Marca presença (1 por dia).</div>
                </div>
                <button class="btn ok" onclick="doCheckin()"><i class="fa-solid fa-check"></i> Check-in</button>
              </div>
            </div>

            <div class="list">
              <div class="it">
                <div>
                  <div style="font-weight:800">Streak</div>
                  <div class="muted" id="uStreakText" style="font-size:12px;margin-top:4px">—</div>
                </div>
                <span class="chip ok" id="uStreakChip">—</span>
              </div>
              <div class="it" style="flex-direction:column; align-items:stretch">
                <div style="display:flex; justify-content:space-between; align-items:center; gap:10px; width:100%">
                  <div>
                    <div style="font-weight:800">Meta semanal</div>
                    <div class="muted" id="uGoalText" style="font-size:12px;margin-top:4px">—</div>
                  </div>
                  <span class="chip" id="uGoalChip">—</span>
                </div>
                <div class="progress" style="margin-top:10px"><div id="uGoalBar"></div></div>
              </div>
            </div>
          </div>

          <div class="sep"></div>

          <div class="card" style="background:rgba(0,0,0,.18); border-radius:16px; border:1px solid var(--line); box-shadow:none">
            <div class="bd" style="padding:14px">
              <div style="display:flex; justify-content:space-between; align-items:center; gap:10px; flex-wrap:wrap">
                <div>
                  <div style="font-weight:900; font-size:14px"><i class="fa-solid fa-stopwatch"></i> Timer de descanso</div>
                  <div class="muted" style="font-size:12px; margin-top:4px">Use 1/2/3 min ou personalizado.</div>
                </div>
                <div class="timerBox">
                  <span class="bigTime" id="tDisplay">00:00</span>
                  <button class="btn" onclick="presetTimer(60)">1m</button>
                  <button class="btn" onclick="presetTimer(120)">2m</button>
                  <button class="btn" onclick="presetTimer(180)">3m</button>
                  <button class="btn primary" onclick="startTimer()"><i class="fa-solid fa-play"></i></button>
                  <button class="btn danger" onclick="stopTimer()"><i class="fa-solid fa-stop"></i></button>
                </div>
              </div>
              <div class="row" style="margin-top:12px">
                <div>
                  <label>Segundos (custom)</label>
                  <input id="tSeconds" inputmode="numeric" placeholder="ex: 90">
                </div>
                <div>
                  <label>&nbsp;</label>
                  <button class="btn" style="width:100%" onclick="applyCustomTimer()"><i class="fa-solid fa-sliders"></i> Aplicar</button>
                </div>
              </div>
            </div>
          </div>

          <div class="sep"></div>

          <div class="twoCol">
            <div class="card" style="box-shadow:none">
              <div class="hd">
                <div>
                  <h2>PR / Cargas</h2>
                  <p>Registre evolução por exercício.</p>
                </div>
              </div>
              <div class="bd">
                <div class="row">
                  <div>
                    <label>Exercício</label>
                    <input id="pr_ex" placeholder="ex: Supino reto">
                  </div>
                  <div>
                    <label>Carga (kg)</label>
                    <input id="pr_kg" inputmode="decimal" placeholder="ex: 60">
                  </div>
                </div>
                <div class="row" style="margin-top:12px">
                  <div>
                    <label>Repetições</label>
                    <input id="pr_reps" inputmode="numeric" placeholder="ex: 8">
                  </div>
                  <div>
                    <label>Observação (opcional)</label>
                    <input id="pr_obs" placeholder="ex: 2 séries boas">
                  </div>
                </div>
                <div class="sep"></div>
                <button class="btn ok" onclick="savePR()"><i class="fa-solid fa-floppy-disk"></i> Salvar PR</button>
                <div class="footerNote" id="prMsg"></div>

                <div class="sep"></div>
                <div class="list" id="uPrList">
                  <div class="it"><div class="muted">Sem PRs carregados.</div><span class="chip">—</span></div>
                </div>
              </div>
            </div>

            <div class="card" style="box-shadow:none">
              <div class="hd">
                <div>
                  <h2>Recados & Histórico</h2>
                  <p>Mensagens do Master e seus últimos treinos.</p>
                </div>
              </div>
              <div class="bd">
                <div class="list" id="uMsgs">
                  <div class="it"><div class="muted">Sem recados.</div><span class="chip">—</span></div>
                </div>

                <div class="sep"></div>

                <div class="list" id="uHistory">
                  <div class="it"><div class="muted">Sem histórico carregado.</div><span class="chip">—</span></div>
                </div>

                <div class="sep"></div>
                <button class="btn" onclick="refreshUser()"><i class="fa-solid fa-rotate"></i> Atualizar dados</button>
                <div class="footerNote" id="userMsg"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Painel menor -->
      <div class="card">
        <div class="hd">
          <div>
            <h2>Atalhos</h2>
            <p>Rápido, simples e sem enrolação.</p>
          </div>
        </div>
        <div class="bd">
          <div class="banner ok">
            <i class="fa-solid fa-bolt"></i>
            <div>
              <div style="font-weight:800">Consistência vence motivação</div>
              <div class="muted" style="font-size:12px;margin-top:4px">Marque o treino concluído e mantenha o streak vivo.</div>
            </div>
          </div>
          <div class="sep"></div>
          <button class="btn danger" onclick="logout()" style="width:100%"><i class="fa-solid fa-right-from-bracket"></i> Sair</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    // ======================
    // CONFIG
    // ======================
    const SCRIPT_URL = "COLE_AQUI_A_URL_DO_SEU_APP_WEB";

    // Sessão local
    const SESSION_KEY = "gymtrack_session_v2";
    let loginMode = "user";
    let session = null;

    // Timer
    let timerSeconds = 0;
    let timerLeft = 0;
    let timerInt = null;

    // ======================
    // HELPERS
    // ======================
    const el = (id)=>document.getElementById(id);

    function setMsg(id, txt, kind=""){
      const e = el(id);
      e.textContent = txt || "";
      e.style.color = kind==="err" ? "rgba(255,77,109,.95)" : (kind==="ok" ? "rgba(43,255,136,.95)" : "");
    }

    function weekdayPt(date=new Date()){
      const d = date.toLocaleDateString("pt-BR",{ weekday:"long" });
      return d.charAt(0).toUpperCase() + d.slice(1);
    }

    function formatBRL(v){
      const n = Number(v || 0);
      return n.toLocaleString("pt-BR",{ style:"currency", currency:"BRL" });
    }

    function daysBetween(a,b){
      const A = new Date(a.getFullYear(),a.getMonth(),a.getDate());
      const B = new Date(b.getFullYear(),b.getMonth(),b.getDate());
      return Math.round((B - A) / 86400000);
    }

    function todayISO(){
      const d = new Date();
      const z = new Date(d.getTime() - d.getTimezoneOffset()*60000);
      return z.toISOString().slice(0,10);
    }

    function renderTime(sec){
      const m = String(Math.floor(sec/60)).padStart(2,'0');
      const s = String(sec%60).padStart(2,'0');
      el("tDisplay").textContent = `${m}:${s}`;
    }

    async function api(action, payload={}){
      if (!SCRIPT_URL || SCRIPT_URL.includes("COLE_AQUI")){
        throw new Error("Defina SCRIPT_URL com a URL do seu App Web.");
      }
      const body = { action, token: session?.token || null, ...payload };
      const res = await fetch(SCRIPT_URL, {
        method: "POST",
        headers: { "Content-Type": "text/plain;charset=utf-8" },
        body: JSON.stringify(body)
      });
      const data = await res.json().catch(()=> ({}));
      if (!res.ok || data.ok === false){
        throw new Error(data.error || ("Falha na API ("+res.status+")"));
      }
      return data;
    }

    function show(view){
      el("viewLogin").classList.add("hidden");
      el("viewMaster").classList.add("hidden");
      el("viewUser").classList.add("hidden");
      el(view).classList.remove("hidden");
    }

    function setLoginMode(mode){
      loginMode = mode;
      el("tabUser").classList.toggle("active", mode==="user");
      el("tabMaster").classList.toggle("active", mode==="master");
      el("loginHint").textContent = mode==="master"
        ? "Master: gerencia usuários, treinos, vencimentos, metas e recados."
        : "Usuário: entra para ver treino, meta, streak, PRs e avisos.";
      setMsg("loginMsg","");
    }

    function saveSession(s){
      session = s;
      localStorage.setItem(SESSION_KEY, JSON.stringify(s));
      el("btnLogout").style.display = "inline-flex";
      el("sessionInfo").textContent = `Logado: ${s.role.toUpperCase()} • ${s.user}`;
    }

    function loadSession(){
      try{
        const raw = localStorage.getItem(SESSION_KEY);
        if (!raw) return null;
        return JSON.parse(raw);
      }catch(e){ return null; }
    }

    function logout(){
      session = null;
      localStorage.removeItem(SESSION_KEY);
      el("btnLogout").style.display = "none";
      el("sessionInfo").textContent = "Não autenticado";
      show("viewLogin");
      setMsg("loginMsg","Sessão encerrada.","ok");
      stopTimer();
    }

    // ======================
    // LOGIN
    // ======================
    async function doLogin(){
      setMsg("loginMsg","Entrando...");
      const user = el("loginUser").value.trim();
      const pass = el("loginPass").value.trim();
      if (!user || !pass){
        setMsg("loginMsg","Preencha usuário e senha.","err");
        return;
      }

      try{
        const data = await api("login", { mode: loginMode, user, pass });
        saveSession({ token: data.token, role: data.role, user: data.user });

        if (data.role === "master"){
          show("viewMaster");
          await refreshMaster();
        } else {
          show("viewUser");
          await refreshUser();
        }
        setMsg("loginMsg","");
      }catch(err){
        setMsg("loginMsg", err.message, "err");
      }
    }

    // ======================
    // MASTER
    // ======================
    async function refreshMaster(){
      setMsg("masterMsg","Carregando KPIs...");
      try{
        const data = await api("master_kpis", {});
        el("kpiTotal").textContent = data.totalUsers ?? "0";
        el("kpiAtivos").textContent = data.activeUsers ?? "0";
        el("kpiReceita").textContent = formatBRL(data.activeRevenue ?? 0);

        el("dueCount").textContent = `${data.dueSoonCount ?? 0} usuário(s) vencendo em até 7 dias`;
        el("inactiveCount").textContent = `${data.inactiveOrNoTrainCount ?? 0} usuário(s) inativos/sem treino recente`;

        setMsg("masterMsg","KPIs atualizados.","ok");
      }catch(err){
        setMsg("masterMsg", err.message, "err");
      }
    }

    async function saveUserMaster(){
      setMsg("masterMsg2","Salvando usuário...");
      try{
        const user = el("m_user").value.trim();
        const pass = el("m_pass").value.trim();
        const mod = el("m_mod").value;
        const modCustom = el("m_mod_custom").value.trim();
        const seq = el("m_seq").value.trim();
        const due = el("m_due").value;
        const status = el("m_status").value;
        const valor = el("m_valor").value.trim();
        const pago = el("m_pago").value;
        const goal = el("m_goal").value.trim();
        const inactDays = el("m_inact_days").value.trim();

        if (!user) throw new Error("Informe o login do usuário.");
        if (!seq) throw new Error("Informe a sequência de treinos.");
        if (!due) throw new Error("Informe o vencimento da mensalidade.");

        const data = await api("master_save_user", {
          user,
          pass: pass || null,
          module: mod,
          moduleCustom: mod==="CUSTOM" ? modCustom : "",
          sequenceText: seq,
          dueDate: due,
          status,
          monthlyValue: valor,
          paid: pago,
          weeklyGoal: goal,
          inactivityDays: inactDays
        });

        setMsg("masterMsg2", data.message || "Salvo com sucesso!", "ok");
        await refreshMaster();
      }catch(err){
        setMsg("masterMsg2", err.message, "err");
      }
    }

    async function loadUserMaster(){
      setMsg("masterMsg2","Buscando usuário...");
      try{
        const user = el("m_user").value.trim();
        if (!user) throw new Error("Informe o login do usuário para buscar.");

        const data = await api("master_get_user", { user });

        el("m_mod").value = data.module || "A";
        el("m_mod_custom").value = data.moduleCustom || "";
        el("m_seq").value = data.sequenceText || "";
        el("m_due").value = (data.dueDate || "").slice(0,10);
        el("m_status").value = data.status || "ATIVO";
        el("m_valor").value = data.monthlyValue || "";
        el("m_pago").value = data.paid ? "SIM" : "NAO";
        el("m_goal").value = data.weeklyGoal || "";
        el("m_inact_days").value = data.inactivityDays || "";

        setMsg("masterMsg2","Usuário carregado.","ok");
      }catch(err){
        setMsg("masterMsg2", err.message, "err");
      }
    }

    async function sendMasterMessage(){
      setMsg("masterMsg2","Enviando recado...");
      try{
        const toUser = el("m_msg_user").value.trim();
        const text = el("m_msg_text").value.trim();
        if (!toUser || !text) throw new Error("Informe o usuário e a mensagem.");

        const data = await api("master_send_message", { user: toUser, text });
        setMsg("masterMsg2", data.message || "Recado enviado.", "ok");
        el("m_msg_text").value = "";
      }catch(err){
        setMsg("masterMsg2", err.message, "err");
      }
    }

    // ======================
    // USER
    // ======================
    async function refreshUser(){
      setMsg("userMsg","Carregando seus dados...");
      try{
        const data = await api("user_get_dashboard", {});

        const nome = data.user || session.user;
        el("uTitle").textContent = `Bem-vindo, ${nome}!`;
        el("uSub").textContent = `${weekdayPt()} • Bora pra cima 💪`;

        const modLabel = data.module === "CUSTOM" ? (data.moduleCustom || "Custom") : (data.module || "—");
        el("uMod").textContent = `Módulo: ${modLabel}`;

        // Treino atual
        const seq = Array.isArray(data.sequence) ? data.sequence : [];
        const idx = Number(data.currentIndex || 0);
        el("uWorkout").textContent = seq[idx] || "Treino não definido ainda.";

        // Aviso mensalidade
        const due = data.dueDate ? new Date(data.dueDate) : null;
        const paid = !!data.paid;
        const status = (data.status || "ATIVO");

        const billingBanner = el("uBillingBanner");
        const inactiveBanner = el("uInactiveBanner");

        // Status
        if (status !== "ATIVO"){
          billingBanner.className = "banner bad";
          billingBanner.classList.remove("hidden");
          el("uBillingText").textContent = "Seu acesso está INATIVO. Fale com a recepção para reativar.";
        } else {
          if (!due){
            billingBanner.classList.add("hidden");
          } else {
            const days = daysBetween(new Date(), due);
            if (!paid && days <= 7){
              billingBanner.className = "banner";
              billingBanner.classList.remove("hidden");
              el("uBillingText").textContent = `Vence em ${days} dia(s) (${due.toLocaleDateString("pt-BR")}). Por favor, efetue o pagamento.`;
            } else {
              billingBanner.classList.add("hidden");
            }
          }
        }

        // Inatividade
        if (data.inactivityAlert){
          inactiveBanner.classList.remove("hidden");
          el("uInactiveText").textContent = data.inactivityText || "Você está há alguns dias sem treinar. Bora voltar!";
        } else {
          inactiveBanner.classList.add("hidden");
        }

        // Streak
        el("uStreakChip").textContent = `${data.streak ?? 0} dias`;
        el("uStreakText").textContent = (data.streak ?? 0) > 0
          ? `Você está mantendo a sequência! Último treino: ${data.lastWorkoutDateBR || "—"}`
          : `Sem sequência ativa. Marque um treino concluído para começar.`;

        // Meta semanal
        const goal = Number(data.weeklyGoal || 0);
        const done = Number(data.weeklyCount || 0);
        el("uGoalChip").textContent = goal ? `${done}/${goal}` : "Sem meta";
        el("uGoalText").textContent = goal
          ? `Você fez ${done} treino(s) nesta semana. Meta: ${goal}.`
          : `O Master ainda não definiu sua meta semanal.`;
        const pct = goal ? Math.min(100, Math.round((done/goal)*100)) : 0;
        el("uGoalBar").style.width = `${pct}%`;

        // Recados
        const msgs = Array.isArray(data.messages) ? data.messages : [];
        const box = el("uMsgs");
        box.innerHTML = "";
        if (!msgs.length){
          box.innerHTML = `<div class="it"><div class="muted">Sem recados.</div><span class="chip">—</span></div>`;
        } else {
          msgs.slice(0,6).forEach(m=>{
            box.insertAdjacentHTML("beforeend", `
              <div class="it">
                <div>
                  <div style="font-weight:800">${m.text}</div>
                  <div class="muted" style="font-size:12px;margin-top:4px">${m.dateBR || ""}</div>
                </div>
                <span class="chip ok">Novo</span>
              </div>
            `);
          });
        }

        // Histórico
        const hist = Array.isArray(data.history) ? data.history : [];
        const h = el("uHistory");
        h.innerHTML = "";
        if (!hist.length){
          h.innerHTML = `<div class="it"><div class="muted">Sem histórico registrado.</div><span class="chip">—</span></div>`;
        } else {
          hist.slice(0,8).forEach(x=>{
            const chipClass = x.type === "CHECKIN" ? "chip ok" : (x.done ? "chip ok" : "chip warn");
            const chipText = x.type === "CHECKIN" ? "Check-in" : (x.done ? "Concluído" : "Pendente");
            h.insertAdjacentHTML("beforeend", `
              <div class="it">
                <div>
                  <div style="font-weight:800">${x.title || "Registro"}</div>
                  <div class="muted" style="font-size:12px;margin-top:4px">${x.dateBR || ""}</div>
                </div>
                <span class="${chipClass}">${chipText}</span>
              </div>
            `);
          });
        }

        // PRs
        renderPRList(Array.isArray(data.prs) ? data.prs : []);

        // reset checkbox
        el("uDone").checked = false;

        setMsg("userMsg","Atualizado.","ok");
      }catch(err){
        setMsg("userMsg", err.message, "err");
      }
    }

    async function markWorkoutDone(){
      if (!el("uDone").checked) return;
      setMsg("userMsg","Registrando conclusão...");
      try{
        const data = await api("user_mark_done", {});
        setMsg("userMsg", data.message || "Boa! Próximo treino liberado.", "ok");
        await refreshUser();
      }catch(err){
        setMsg("userMsg", err.message, "err");
        el("uDone").checked = false;
      }
    }

    async function doCheckin(){
      setMsg("userMsg","Fazendo check-in...");
      try{
        const data = await api("user_checkin", {});
        setMsg("userMsg", data.message || "Check-in registrado!", "ok");
        await refreshUser();
      }catch(err){
        setMsg("userMsg", err.message, "err");
      }
    }

    function renderPRList(prs){
      const list = el("uPrList");
      list.innerHTML = "";
      if (!prs.length){
        list.innerHTML = `<div class="it"><div class="muted">Sem PRs carregados.</div><span class="chip">—</span></div>`;
        return;
      }
      prs.slice(0,8).forEach(p=>{
        const right = `${p.kg ?? ""}kg • ${p.reps ?? ""} reps`;
        list.insertAdjacentHTML("beforeend", `
          <div class="it">
            <div>
              <div style="font-weight:800">${p.exercise || "Exercício"}</div>
              <div class="muted" style="font-size:12px;margin-top:4px">${p.dateBR || ""} ${p.note ? "• "+p.note : ""}</div>
            </div>
            <span class="chip ok">${right}</span>
          </div>
        `);
      });
    }

    async function savePR(){
      setMsg("prMsg","Salvando PR...");
      try{
        const exercise = el("pr_ex").value.trim();
        const kg = el("pr_kg").value.trim();
        const reps = el("pr_reps").value.trim();
        const note = el("pr_obs").value.trim();
        if (!exercise || !kg || !reps) throw new Error("Preencha exercício, carga e repetições.");

        const data = await api("user_save_pr", { exercise, kg, reps, note });
        setMsg("prMsg", data.message || "PR salvo!", "ok");

        el("pr_ex").value = "";
        el("pr_kg").value = "";
        el("pr_reps").value = "";
        el("pr_obs").value = "";

        await refreshUser();
      }catch(err){
        setMsg("prMsg", err.message, "err");
      }
    }

    // ======================
    // TIMER
    // ======================
    function presetTimer(sec){
      timerSeconds = sec;
      timerLeft = sec;
      renderTime(timerLeft);
    }
    function applyCustomTimer(){
      const v = Number(el("tSeconds").value || 0);
      if (!v || v < 5){ return; }
      timerSeconds = v;
      timerLeft = v;
      renderTime(timerLeft);
    }
    function startTimer(){
      if (!timerLeft) return;
      if (timerInt) return;
      timerInt = setInterval(()=>{
        timerLeft--;
        renderTime(Math.max(0,timerLeft));
        if (timerLeft <= 0){
          stopTimer();
          try{
            // beep simples
            const ctx = new (window.AudioContext || window.webkitAudioContext)();
            const o = ctx.createOscillator();
            const g = ctx.createGain();
            o.type = "sine";
            o.frequency.value = 880;
            o.connect(g); g.connect(ctx.destination);
            g.gain.value = 0.08;
            o.start();
            setTimeout(()=>{ o.stop(); ctx.close(); }, 450);
          }catch(e){}
        }
      }, 1000);
    }
    function stopTimer(){
      if (timerInt){ clearInterval(timerInt); timerInt = null; }
    }

    // ======================
    // INIT
    // ======================
    (function init(){
      setLoginMode("user");
      renderTime(0);

      const s = loadSession();
      if (s && s.token && s.role){
        session = s;
        el("btnLogout").style.display = "inline-flex";
        el("sessionInfo").textContent = `Logado: ${s.role.toUpperCase()} • ${s.user}`;
        if (s.role === "master"){
          show("viewMaster");
          refreshMaster();
        } else {
          show("viewUser");
          refreshUser();
        }
      }
    })();
  </script>
</body>
</html>
