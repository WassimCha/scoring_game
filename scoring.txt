import sys


class Scoring:

    def __init__(self,player1,player2):
        # Define Constructor
        self.player1 = player1
        self.player2 = player2
        self.score_player1 = 0
        self.score_player2 = 0
        self.advantage = ''

    def add_to_score(self,player):
        # This function is to add score to the player 'player'
        # It takes a player as argument and add the appropriate score to his score

        if player == self.player1:
            if self.score_player1 == 30:
                self.score_player1 = 40
            elif self.score_player1 == 40:
                self.manage_advantage(player)
            else:
                self.score_player1 += 15

        if player == self.player2:
            if self.score_player2 == 30:
                self.score_player2 = 40
            elif self.score_player2 == 40:
                self.manage_advantage(player)
            else:
                self.score_player2 += 15
        return True

    def manage_advantage(self,player):
        # Manage the advantage between players to know who will win the match
        if self.advantage == '':
            if player == self.player1:
                if self.score_player1 == 40 and self.score_player2 != 40:
                    print('Congratulation!! : ' + player + ' win The Match')
                    sys.exit()
                else:
                    self.advantage = player

            if player == self.player2:
                if self.score_player1 != 40 and self.score_player2 == 40:
                    print('Congratulation!! : ' + player + ' win The Match')
                    sys.exit()
                else:
                    self.advantage = player

            print('Advantage with '+ player)
        elif self.advantage == player:
            print('Congratulation!! : ' + player + ' win The Match')
            sys.exit()
        else:
            print('Advantage is Free')
            self.advantage = ''

    def score(self,player):
        print('----------------------------\n'+player + ' Score one Goaaal')
        if player == self.player1:
            self.add_to_score(player)

        elif player == self.player2:
            self.add_to_score(player)
        else:
            print('Please choose a correct name for the player')

        print('Score ' + self.player1 + ' = ' + str(self.score_player1))
        print('Score ' + self.player2 + ' = ' + str(self.score_player2))



def main():
    player1 = 'James'
    player2 = 'Wassim'
    game1 = Scoring(player1, player2)

    while True:
        the_player = input('choose who mark ' + player1 + ' or ' + player2 + ': ')
        game1.score(the_player)


if __name__ == '__main__':
    main()
# game1.score('james')
# game1.score('Wassim')
# game1.score('james')
# game1.score('Wassim')
# game1.score('james')
# game1.score('Wassim')
# game1.score('james')
# game1.score('Wassim')
# game1.score('Wassim')
# game1.score('Wassim')
# game1.score('Wassim')
# game1.score('Wassim')



