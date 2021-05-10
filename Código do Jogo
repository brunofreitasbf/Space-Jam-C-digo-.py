import pygame
pygame.init()

#jogador
x = 0
y = 130

#naveA
pos_x = 305
pos_y = -325
#naveB
posB_x = -290
posB_y = -325
#naveC
posC_x = 10
posC_y = -325

timer = 0
timerB = 0

velocidade = 15
velocidadeA = 10
velocidadeB = 10
velocidadec = 12

fundo = pygame.image.load('fundo_espaço.png')
jogador = pygame.image.load('jogador.png')
naveA = pygame.image.load('nave_A.png')
naveB = pygame.image.load('nave_B.png')
naveC = pygame.image.load('nave_C.png')

font = pygame.font.SysFont('SpaceJam',50)
texto = font.render("Score: ",True, (255,255,255), (0,0,0))
pos_texto = texto.get_rect()
pos_texto.center = (415,15)

janela = pygame.display.set_mode((800,600))
pygame.display.set_caption("Armadilha Espacial")

janela_aberta = True
while janela_aberta:
    pygame.time.delay(20)
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            janela_aberta = False

    comandos = pygame.key.get_pressed()
    if comandos[pygame.K_UP] and (y >= -253):
        y -= velocidade
    if comandos[pygame.K_DOWN] and (y <= 190):
        y += velocidade
    if comandos[pygame.K_RIGHT] and (x <= 311):
        x += velocidade
    if comandos[pygame.K_LEFT] and (x >= -320):
        x -= velocidade

    if (pos_y >= 600):
        pos_y = -500
        if velocidadeA<70:
            velocidadeA += 2.4
    if (posB_y >= 600):
        posB_y = -500
        if velocidadeB<70:
           velocidadeB += 1.8
    if (posC_y >= 600):
        posC_y = -500
        if velocidadeC<70:
           velocidadeC += 2.2

    pos_y += velocidadeA
    posB_y += velocidadeB
    posC_y += velocidadeC

    if (timer <10):
        timer +=1
    else:
        timerB +=1
        texto = font.render("Score: "+str(timerB),True, (255,255,255), (0,0,0))
        timer = 0;

    janela.blit(fundo, (0, 0))
    janela.blit(jogador, (x, y))
    janela.blit(naveA, (pos_x, pos_y))
    janela.blit(naveB, (posB_x, posB_y))
    janela.blit(naveC, (posC_x, posC_y))
    janela.blit(texto, pos_texto)

    pygame.display.update.update()

pygame.quit()
