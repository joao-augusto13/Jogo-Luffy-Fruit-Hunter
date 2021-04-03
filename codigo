import pygame
pygame.mixer.pre_init(frequency=44100)
pygame.init()
pygame.mixer.init(frequency=44100)


x = 340
y = 450
pos_fruta1x = 130
pos_fruta1y = -270
pos_fruta2y = -250
pos_fruta2x = 330
pos_fruta3y = -230
pos_fruta3x = 530
pos_carnex = 140
pos_carney = -1500
pos_aguay = -2000
pos_aguax = 540
velocidade = 200
vel_fruta1 = 10
vel_fruta2 = 10
vel_fruta3 = 10



pontos = 0
font = pygame.font.Font("freesansbold.ttf", 32)
text = font.render("Pontuacao: "+str(pontos), True, (255,0,0), (0,0,0))
textRect = text.get_rect()
textRect.center = (100, 30)

vidas = 5
font2 = pygame.font.Font("freesansbold.ttf", 32)
text2 = font.render("Vidas: "+str(vidas), True, (255,0,0), (0,0,0))
textRect2 = text.get_rect()
textRect2.center = (100, 60)

font3 = pygame.font.Font("freesansbold.ttf", 100)
text3 = font.render("Fim de Jogo", True,(255,0,0), (0,0,0))
textRect3 = text.get_rect()
textRect3.center = (-1400, 200)




fundo = pygame.image.load("Fundo Verde.png")
jogador = pygame.image.load("luffy.png")
fruta1 = pygame.image.load("fruta 1.png")
fruta2 = pygame.image.load("fruta 2.png")
fruta3 = pygame.image.load("fruta 3.png")
carne = pygame.image.load("carne.png")
agua = pygame.image.load("agua.png")

janela = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Jogo")
pygame.mixer.music.load("musica de fundo.wav")
pygame.mixer.music.play(-1)

som_carne = pygame.mixer.Sound("som da carne.wav")
som_agua = pygame.mixer.Sound("Som da agua.wav")

# movimentacao

janela_aberta = True
while janela_aberta:
    pygame.time.delay(50)

    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            janela_aberta = False
    direcoes = pygame.key.get_pressed()
    if direcoes[pygame.K_RIGHT] and x <=500:
            x+= velocidade
    if direcoes[pygame.K_d] and x <=500:
            x+= velocidade
    if direcoes[pygame.K_LEFT] and x >= 150:
            x-= velocidade
    if direcoes[pygame.K_a] and x >=150:
            x-= velocidade

#colisoes

    if pos_fruta1y + 80 == y + 10 and x == 140:
        pontos = pontos + 5
        text = font.render("Pontuacao: " + str(pontos), True, (255, 0, 0), (0, 0, 0))
        pos_fruta1y = -270
        
    if pos_fruta2y + 80 == y + 10 and x == 340:
        pontos = pontos + 5
        text = font.render("Pontuacao: " + str(pontos), True, (255, 0, 0), (0, 0, 0))
        pos_fruta2y = -250

    if pos_fruta3y + 80 == y + 10 and x == 540:
        pontos = pontos + 5
        text = font.render("Pontuacao: " + str(pontos), True, (255, 0, 0), (0, 0, 0))
        pos_fruta3y = -230

    if pos_carney + 80 == y + 10 and x == 140:
        som_carne.play()
        vidas = vidas + 1
        text2 = font.render("Vidas: " + str(vidas), True, (255, 0, 0), (0, 0, 0))
        pos_carney = -1500 -10

    if pos_aguay + 80 == y + 10 and x == 540:
        som_agua.play()
        vidas = vidas - 1
        text2 = font.render("Vidas: " + str(vidas), True, (255, 0, 0), (0, 0, 0))
        pos_aguay = -2000

#Animacao

    if pos_fruta1y + 80 < 800:
        pos_fruta1y += vel_fruta1
    if pos_fruta1y + 80 == 800:
        pos_fruta1y = -270
        vidas = vidas - 1
        text2 = font.render("Vidas: " + str(vidas), True, (255, 0, 0), (0, 0, 0))

    if pos_fruta2y + 80 < 800:
        pos_fruta2y += vel_fruta2
    if pos_fruta2y + 80 == 800:
        pos_fruta2y = -250
        vidas = vidas - 1
        text2 = font.render("Vidas: " + str(vidas), True, (255, 0, 0), (0, 0, 0))

    if pos_fruta3y + 80 < 800:
        pos_fruta3y += vel_fruta3
    if pos_fruta3y + 80 == 800:
        pos_fruta3y = -230
        vidas = vidas - 1
        text2 = font.render("Vidas: " + str(vidas), True, (255, 0, 0), (0, 0, 0))

    if pos_carney + 80 < 800:
        pos_carney += 5
    if pos_carney + 80 == 800:
        pos_carney = -1500 -10

    if pos_aguay + 80 < 800:
        pos_aguay += 10
    if pos_aguay + 80 == 800:
        pos_aguay = -2000


    if vidas == 0:
        y = -10000
        textRect = (340, 300)
        textRect2 = (-1500, 150)
        textRect3 = (200, 100)


#adicionar as imagens a janela

    janela.blit(fundo,(0, 0))
    janela.blit(jogador, (x, y))
    janela.blit(fruta1, (pos_fruta1x, pos_fruta1y))
    janela.blit(fruta2, (pos_fruta2x, pos_fruta2y))
    janela.blit(fruta3, (pos_fruta3x, pos_fruta3y))
    janela.blit(text, textRect)
    janela.blit(text2, textRect2)
    janela.blit(text3, textRect3)
    janela.blit(carne, (pos_carnex, pos_carney))
    janela.blit(agua, (pos_aguax, pos_aguay))
    pygame.display.update()


pygame.quit()
