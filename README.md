<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MiniMercado SuperUtil</title>

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

    <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Poppins', Arial, sans-serif;
        background: linear-gradient(to right, #f4f4f4, #e9ecef);
        color: #003d14;
        padding: 0;
        line-height: 1.6;
    }

    header {
        background-color: #790000;
        color: white;
        padding: 20px 40px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    header h1 {
        font-size: 2em;
    }

    nav a {
        color: white;
        text-decoration: none;
        margin: 0 15px;
        font-weight: 500;
    }

    nav a:hover {
        text-decoration: underline;
    }

    .main-content-wrapper {
        display: flex; /* Enable flexbox for sidebars and main content */
        justify-content: space-between; /* Space out the columns */
        max-width: 1400px; /* Increased max-width to accommodate wider sidebars */
        margin: 20px auto; /* Center the wrapper */
    }

    .container {
        flex-grow: 1; /* Allow main content to grow */
        max-width: 800px; /* Adjust max-width for main content */
        background: white;
        padding: 30px;
        border-radius: 16px;
        box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        margin: 0 20px; /* Add some horizontal margin */
    }

    h2 {
        color: #790000;
        font-size: 1.8em;
        margin-top: 20px;
    }

    .produto, .servico {
        background-color: #fff;
        border-radius: 12px;
        box-shadow: 0 4px 10px rgba(0,0,0,0.08);
        padding: 15px;
        margin: 20px 0;
        display: flex;
        align-items: center;
        gap: 15px;
    }

    .produto img, .servico img {
        width: 100px;
        height: 100px;
        border-radius: 12px;
        object-fit: cover;
    }

    .produto-info, .servico-info {
        flex: 1;
    }

    button {
        background: linear-gradient(to right, #3498db, #2e86de);
        color: white;
        border: none;
        padding: 10px 16px;
        border-radius: 20px;
        cursor: pointer;
        font-weight: 600;
        transition: background 0.3s ease, transform 0.2s ease;
    }

    button:hover {
        background: linear-gradient(to right, #2980b9, #2471a3);
        transform: translateY(-2px);
    }

    footer {
        background-color: #f4f4f4;
        text-align: center;
        padding: 20px;
        font-size: 0.85em;
        color: #555;
        margin-top: 40px;
    }

    footer a {
        color: #003d14;
        margin: 0 10px;
        text-decoration: none;
    }

    footer a:hover {
        text-decoration: underline;
    }

    .carousel img {
        max-height: 400px;
        object-fit: cover;
    }

    /* Left Sidebar for Agendamento */
    .sidebar-left {
        width: 380px; /* Increased width */
        background-color: white;
        border-radius: 0 12px 12px 0; /* Adjusted for left side */
        box-shadow: 4px 0 10px rgba(0, 0, 0, 0.2); /* Adjusted shadow for left side */
        padding: 20px;
        z-index: 1000;
        margin-right: 20px; /* Space between sidebar and main content */
    }

    .sidebar-left h3 {
        color: #790000;
        margin-bottom: 15px; /* Added spacing below heading */
        text-align: center;
    }

    /* Grouping for labels and inputs in forms */
    .form-group {
        margin-bottom: 15px; /* Spacing between form groups */
    }

    .form-group label {
        display: block; /* Each label on its own line */
        margin-bottom: 5px; /* Small space between label and input */
        font-weight: 600; /* Make labels a bit bolder */
        color: #333;
    }

    .sidebar-left input[type="text"],
    .sidebar-left input[type="date"],
    .sidebar-left input[type="time"],
    .sidebar-left select,
    .sidebar-left textarea,
    .sidebar-right input[type="text"],
    .sidebar-right input[type="tel"],
    .sidebar-right input[type="email"],
    .sidebar-right input[type="number"],
    .sidebar-right textarea {
        width: 100%; /* Keep full width for inputs for consistency */
        padding: 8px;
        border-radius: 8px;
        border: 1px solid #ccc;
        box-sizing: border-box; /* Include padding in width calculation */
    }

    /* Specific styles for radio buttons and checkboxes to align them better */
    .sidebar-left input[type="radio"],
    .sidebar-left input[type="checkbox"],
    .sidebar-right input[type="radio"],
    .sidebar-right input[type="checkbox"] {
        width: auto; /* Allow auto width for radio/checkbox */
        margin-right: 5px; /* Space between checkbox/radio and its label */
    }

    .sidebar-left label[for="retirada"],
    .sidebar-left label[for="teleentrega"],
    .sidebar-right label[for="masculino"],
    .sidebar-right label[for="feminino"],
    .sidebar-right label[for="outro"],
    .sidebar-right label[for="promocoes"],
    .sidebar-right label[for="novidades"] {
        display: inline-block; /* Keep these labels next to their inputs */
        margin-bottom: 5px;
        font-weight: normal; /* Reset font-weight for these specific labels */
        color: #000; /* Adjust color if needed */
    }


    .sidebar-left button,
    .sidebar-right button {
        width: 100%;
        padding: 10px; /* Slightly more padding for buttons */
        margin-top: 20px; /* More space above the button */
        background: linear-gradient(to right, #3498db, #2e86de);
        color: white;
        border: none;
        border-radius: 20px; /* Rounded buttons */
        cursor: pointer;
        font-weight: 600;
        transition: background 0.3s ease, transform 0.2s ease;
    }

    .sidebar-left button:hover,
    .sidebar-right button:hover {
        background: linear-gradient(to right, #2980b9, #2471a3);
        transform: translateY(-2px);
    }

    /* Right Sidebar for Cadastro */
    .sidebar-right {
        width: 380px; /* Increased width */
        background-color: white;
        border-radius: 12px 0 0 12px;
        box-shadow: -4px 0 10px rgba(0, 0, 0, 0.2);
        padding: 20px;
        z-index: 1000;
        margin-left: 20px; /* Space between main content and sidebar */
    }

    .sidebar-right h3 {
        color: #790000;
        margin-bottom: 15px; /* Added spacing below heading */
        text-align: center;
    }


    /* Relógio no Footer */
    .relogio {
        font-weight: bold;
        color: #333;
    }

    </style>
</head>
<body>

    <header>
        <h1>MiniMercado SuperUtil</h1>
        <nav>
            <a href="#produtos">Produtos</a>
            <a href="#servicos">Serviços</a>
            <a href="#contato">Contato</a>
            <a href="#localizacao">Localização</a>
        </nav>
    </header>

    <div id="carouselExample" class="carousel slide" data-bs-ride="carousel">
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src="https://media.istockphoto.com/id/1157106624/pt/foto/all-your-necessities-stored-in-one-place.jpg?s=612x612&w=0&k=20&c=QADz-fF7X_vN3fh4CabC8Xsw0zGVNQret6gZJozlw2o=" class="d-block w-100" alt="Banner com produtos do minimercado">
            </div>
            <div class="carousel-item">
                <img src="https://i0.wp.com/www.opuspesquisa.com/wp-content/uploads/2021/03/Pesquisa-de-mercado-para-supermercado.png?resize=730%2C441&ssl=1" class="d-block w-100" alt="Cesta com alimentos variados">
            </div>
            <div class="carousel-item">
                <img src="https://b3068395.smushcdn.com/3068395/wp-content/uploads/2019/08/shutterstock_365425265_Easy-Resize.com_-1024x576.jpg?lossy=2&strip=1&webp=1" class="d-block w-100" alt="Pães frescos no mercado">
            </div>
        </div>
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Anterior</span>
        </button>
        <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
            <span class="visually-hidden">Próximo</span>
        </button>
    </div>

    <div class="main-content-wrapper">
        <div class="sidebar-left">
            <h3>Agendamento de Pedido</h3>
            <form id="formAgendamento">
                <div class="form-group">
                    <label>Escolha o serviço:</label><br>
                    <input type="radio" id="retirada" name="servico" value="Retirada no local" required>
                    <label for="retirada">Retirada no local</label><br>

                    <input type="radio" id="teleentrega" name="servico" value="Tele-entrega">
                    <label for="teleentrega">Tele-entrega</label>
                </div>

                <div class="form-group">
                    <label for="data">Escolha a data:</label>
                    <input type="date" id="data" name="data" required>
                </div>

                <div class="form-group">
                    <label for="horario">Escolha o horário:</label>
                    <input type="time" id="horario" name="horario" required>
                </div>

                <button type="submit">Agendar</button>
            </form>
        </div>

        <div class="container">
            <section id="produtos">
                <h2>Produtos por Categoria</h2>

                <h3>Arroz</h3>
                <div class="produto">
                    <img src="https://cdn.awsli.com.br/2500x2500/2777/2777231/produto/309423083/arroz-integral-agulhinha-3b0z5toile.jpg" alt="Arroz Integral">
                    <div class="produto-info">
                        <strong>Arroz Integral Kaka - 1kg</strong><br>
                        <p>R$8,00</p>
                        <button>Comprar</button>
                    </div>
                </div>
                <div class="produto">
                    <img src="https://i.panelinha.com.br/i1/bk-9384-arroz-branco-soltinho.webp" alt="Arroz Branco">
                    <div class="produto-info">
                        <strong>Arroz Branco Kaka - 1kg</strong><br>
                        <p>R$7,00</p>
                        <button>Comprar</button>
                    </div>
                </div>

                <h3>Feijão</h3>
                <div class="produto">
                    <img src="https://emporio4estrelas.vtexassets.com/arquivos/ids/158089/Feijao-Bolinha-Vermelho-500g.png?v=636930952012630000" alt="feijão vermelho">
                    <div class="produto-info">
                        <strong>Feijão Vermelho Serrano - 1kg</strong><br>
                        <p>R$6,00</p>
                        <button>Comprar</button>
                    </div>
                </div>
                <div class="produto">
                    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT5Mamf8dUUG1tE8hFfCoyXchyl7fCFFxP4Yi3Byxb2d8-TWyxiMMhiDV0bI2b54eaLaIg&usqp=CAU" alt="Feijão Preto">
                    <div class="produto-info">
                        <strong>Feijão Preto Serrano - 1kg</strong><br>
                        <p>R$5,50</p>
                        <button>Comprar</button>
                    </div>
                </div>

                <h3>Macarrão</h3>
                <div class="produto">
                    <img src="https://www.wikihow.com/images_en/thumb/1/17/Make-Spaghetti-Step-7-Version-8.jpg/v4-460px-Make-Spaghetti-Step-7-Version-8.jpg" alt="Espaguete">
                    <div class="produto-info">
                        <strong>Espaguete Orquidea - 500g</strong><br>
                        <p>R$4,00</p>
                        <button>Comprar</button>
                    </div>
                </div>
                <div class="produto">
                    <img src="https://phygital-files.mercafacil.com/tartufo-bucket/uploads/produto/penne_cozido_230g_fad33e48-c684-46d5-8adf-52b6aea64f0e.png" alt="Penne">
                    <div class="produto-info">
                        <strong>Macarrão Penne Orquidea - 500g</strong><br>
                        <p>R$4,50</p>
                        <button>Comprar</button>
                    </div>
                </div>
            </section>

            <section id="servicos">
                <h2>Serviços Oferecidos</h2>
                <div class="servico">
                    <img src="https://img.freepik.com/vetores-premium/entregador-montando-a-ilustracao-de-scooter-vermelho_9845-14.jpg?semt=ais_hybrid&w=740" alt="TeleEntrega">
                    <div class="servico-info">
                        <strong>TeleEntrega</strong>
                        <p>Entregamos na sua casa com agilidade.</p>
                        <p><strong>Valor:</strong> R$5,00 por entrega</p>
                    </div>
                </div>
                <div class="servico">
                    <img src="https://blog.cestanobre.com.br/wp-content/uploads/2017/04/legislacao-da-cesta-basica-tire-aqui-suas-duvidas.jpeg" alt="Cesta Básica">
                    <div class="servico-info">
                        <strong>Montagem de Cesta Básica</strong>
                        <p>Montamos cestas básicas personalizadas para sua família ou empresa.</p>
                        <p><strong>Valor:</strong> A partir de R$40,00</p>
                    </div>
                </div>
            </section>

            <section id="contato">
                <h2>Contato</h2>
                <p>Telefone para TeleEntrega: (51) 1234-5678 <button>Fazer Pedido</button></p>
                <p>Email: minimercadosutil@gmail.com</p>
            </section>

            <section id="localizacao">
                <h2>Localização</h2>
                <p>Rua das Flores, 123 - Centro - Porto Alegre/RS</p>
                <button>Ver no Mapa</button>
            </section>

            <section>
                <h2>Horário de Funcionamento</h2>
                <p>Segunda a Sexta: 08:00 - 20:00</p>
                <p>Sábado: 08:00 - 18:00</p>
                <p>Domingo: Fechado</p>
            </section>

            <section>
                <h2>Formas de Pagamento</h2>
                <ul>
                    <li>Dinheiro</li>
                    <li>Cartão de Débito</li>
                    <li>Cartão de Crédito</li>
                    <li>Pix</li>
                </ul>
            </section>
        </div>

        <div class="sidebar-right">
            <h3>Cadastro de Cliente</h3>
            <form id="formCadastro">
                <div class="form-group">
                    <label for="nome">Nome:</label>
                    <input type="text" id="nome" name="nome" placeholder="Digite seu nome completo" required>
                </div>

                <div class="form-group">
                    <label for="endereco">Endereço:</label>
                    <input type="text" id="endereco" name="endereco" placeholder="Rua, nº, bairro, cidade" required>
                </div>

                <div class="form-group">
                    <label for="cpf">CPF:</label>
                    <input type="text" id="cpf" name="cpf" placeholder="000.000.000-00" pattern="\d{3}\.\d{3}\.\d{3}-\d{2}" required>
                </div>

                <div class="form-group">
                    <label>Sexo:</label><br>
                    <input type="radio" id="masculino" name="sexo" value="Masculino" required>
                    <label for="masculino">Masculino</label><br>

                    <input type="radio" id="feminino" name="sexo" value="Feminino">
                    <label for="feminino">Feminino</label><br>

                    <input type="radio" id="outro" name="sexo" value="Outro">
                    <label for="outro">Outro</label>
                </div>

                <div class="form-group">
                    <label for="telefone">Telefone:</label>
                    <input type="tel" id="telefone" name="telefone" placeholder="(00) 00000-0000" pattern="\(\d{2}\) \d{5}-\d{4}" required>
                </div>

                <div class="form-group">
                    <label for="email">E-mail:</label>
                    <input type="email" id="email" name="email" placeholder="seuemail@exemplo.com" required>
                </div>

                <div class="form-group">
                    <label for="idade">Idade:</label>
                    <input type="number" id="idade" name="idade" min="10" max="120" required>
                </div>

                <div class="form-group">
                    <label>Preferências:</label><br>
                    <input type="checkbox" id="promocoes" name="preferencias" value="Receber Promoções">
                    <label for="promocoes">Receber Promoções</label><br>

                    <input type="checkbox" id="novidades" name="preferencias" value="Receber Novidades">
                    <label for="novidades">Receber Novidades</label>
                </div>

                <div class="form-group">
                    <label for="observacoes">Observações:</label>
                    <textarea id="observacoes" name="observacoes" placeholder="Digite aqui se tiver alguma observação..." rows="3"></textarea>
                </div>

                <button type="submit">Cadastrar</button>
            </form>
        </div>
    </div>

    <footer>
        <p>&copy; 2024 MiniMercado SuperUtil. Todos os direitos reservados.</p>
        <p>Desenvolvido por Cainã Adorne</p>
        <nav>
            <a href="#produtos">Produtos</a> |
            <a href="#servicos">Serviços</a> |
            <a href="#contato">Contato</a> |
            <a href="#localizacao">Localização</a>
            <p class="relogio" id="relogio"></p>

        </nav>
    </footer>
    <script>

    document.getElementById('formAgendamento').addEventListener('submit', function(event) {
        event.preventDefault();
        const servico = document.querySelector('input[name="servico"]:checked').value;
        const data = document.getElementById('data').value;
        const horario = document.getElementById('horario').value;
        alert(`Agendamento realizado!\nServiço: ${servico}\nData: ${data}\nHorário: ${horario}`);
        this.reset();
    });


    // Função para atualizar o relógio
    function atualizarRelogio() {
        const agora = new Date();
        const horas = agora.getHours().toString().padStart(2, '0');
        const minutos = agora.getMinutes().toString().padStart(2, '0');
        const segundos = agora.getSeconds().toString().padStart(2, '0');
        const horarioAtual = `${horas}:${minutos}:${segundos}`;
        document.getElementById('relogio').textContent = `Horário atual: ${horarioAtual}`;
    }

    // Atualiza o relógio a cada segundo
    setInterval(atualizarRelogio, 1000);
    atualizarRelogio(); // Executa imediatamente ao carregar

    // Mensagem ao cadastrar
    document.getElementById('formCadastro').addEventListener('submit', function(event) {
        event.preventDefault();
        alert("Cadastro realizado com sucesso!");
        this.reset();
    });

    </script>
</body>
</html>

