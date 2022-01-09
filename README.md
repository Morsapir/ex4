# This document presents the final (last) assignment for the OOP course (CS.Ariel 2021),
# I am design a “Pokemon game” in which given a weighted graph,  a set of “Agents” should be located on it so they could “catch” as many “Pokemons” as possible. The pokemons are located on the graph’s (directed) edges, therefore, the agent needs to take (aka walk)  the proper edge to “grab” the pokemon

#This project contains two class

# 1 class Client:

    def start_connection(self, ip, port):
        """
        use with ip='127.0.0.1' , port=6666
        to start a new connection to the game server
        """
    

    def __send_message(self, msg):
    

    def get_agents(self):
        """
        returns: json str of agents. for example:\n
        {
            "Agents":[
                {
                    "Agent":
                    {
                        "id":0,
                        "value":0.0,
                        "src":0,
                        "dest":1,
                        "speed":1.0,
                        "pos":"35.18753053591606,32.10378225882353,0.0"
                    }
                }
            ]
        }
        """
      

    def add_agent(self, json_of_node):
        """
        param json_of_node should be in this format: '{"id":0}'
        (replace 0 with the desired starting node for the agent.)
        returns 'true' (as str) iff the agent has been added succesfuly
        """
      

    def get_graph(self):
        """
        returns the graph as json str. for example:\n
        {
            "Edges":[
                {
                    "src":0,
                    "w":1.4004465106761335,
                    "dest":1
                },
                {
                    "src":0,
                    "w":1.4620268165085584,
                    "dest":10
                }
            ],
            "Nodes":[
                {
                    "pos":"35.18753053591606,32.10378225882353,0.0",
                    "id":0
                },
                {
                    "pos":"35.18958953510896,32.10785303529412,0.0",
                    "id":1
                },
                {
                    "pos":"35.19341035835351,32.10610841680672,0.0",
                    "id":10
                }
            ]
        }
        """

    def get_info(self):
        """
        returns the current game info. for example:\n
        {
            "GameServer":{
                "pokemons":1,
                "is_logged_in":false,
                "moves":1,
                "grade":0,
                "game_level":0,
                "max_user_level":-1,
                "id":0,
                "graph":"data/A0",
                "agents":1
            }
        }
        """
        res = self.__send_message("getInfo")
        return res

    def get_pokemons(self):
        """
        returns the current pokemons state as json str.\n
        for pokemon lying on edge (src,dest), then:\n
        src < dest => type > 0\n
        dest < src => type < 0\n
        example:\n
        {
            "Pokemons":[
                {
                    "Pokemon":{
                        "value":5.0,
                        "type":-1,
                        "pos":"35.197656770719604,32.10191878639921,0.0"
                    }
                }
            ]
        }

        """
    

    def is_running(self):
        """
        returns 'true' (as str) if the game is still running,
        else: returns 'false' (also str)
        """
       
    def time_to_end(self):
        """
        returns time to end in mili-seconds str.
        for example: '29996'
        """
     
    def start(self):
        """
        use start to run the game
        """

    def stop(self):
        """
        use stop to end the game and upload results.
        Note: results will be uploaded only after login and scores > 0.
        """

    def move(self):
        """
        activate all valid choose_next_edge calls.
        returns: agents state with the same form as get_agents()
        """
     
    def choose_next_edge(self, next_agent_node_json):
        """
        choosing the next destination for a specific agent.
        param: next_agent_node_json should be in format:\n
        '{"agent_id":0, "next_node_id":1}'.
        Note that if\n
        1. the agent is still moving on some edge, (a.k. agent.dest != -1)
        or 2. the "next_node_id" isn't an adjacent vertex of agent.src,
        then move() won't be affected by this invalid "next_node_id" choice.
        """

    def log_in(self, id_str):
        """
        enter your id as str to login and upload your score to the web server
        """

    def stop_connection(self):
        """
        use it to close the connection 'gracefuly'
    
# 2 studentcode- server code 



the result-
![image](https://user-images.githubusercontent.com/92923336/148697771-52bb661b-4a21-4aed-b75e-962f063081b2.png)
0- {"GameServer":{"pokemons":1,"is_logged_in":false,"moves":1827,"grade":79,"game_level":0,"max_user_level":-1,"id":0,"graph":"data/A0","agents":1}}
1-{"GameServer":{"pokemons":2,"is_logged_in":false,"moves":3669,"grade":125,"game_level":1,"max_user_level":-1,"id":0,"graph":"data/A0","agents":1}}
2-{"GameServer":{"pokemons":3,"is_logged_in":false,"moves":1828,"grade":166,"game_level":2,"max_user_level":-1,"id":0,"graph":"data/A0","agents":1}}
3-{"GameServer":{"pokemons":4,"is_logged_in":false,"moves":3670,"grade":342,"game_level":3,"max_user_level":-1,"id":0,"graph":"data/A0","agents":1}}
4-{"GameServer":{"pokemons":5,"is_logged_in":false,"moves":1828,"grade":110,"game_level":4,"max_user_level":-1,"id":0,"graph":"data/A1","agents":1}}
5-{"GameServer":{"pokemons":6,"is_logged_in":false,"moves":3665,"grade":166,"game_level":5,"max_user_level":-1,"id":0,"graph":"data/A1","agents":1}}
6-{"GameServer":{"pokemons":1,"is_logged_in":false,"moves":1835,"grade":40,"game_level":6,"max_user_level":-1,"id":0,"graph":"data/A1","agents":1}}
7-{"GameServer":{"pokemons":2,"is_logged_in":false,"moves":3671,"grade":125,"game_level":7,"max_user_level":-1,"id":0,"graph":"data/A1","agents":1}}
8-{"GameServer":{"pokemons":3,"is_logged_in":false,"moves":1831,"grade":0,"game_level":8,"max_user_level":-1,"id":0,"graph":"data/A2","agents":1}}
9-{"GameServer":{"pokemons":4,"is_logged_in":false,"moves":3654,"grade":0,"game_level":9,"max_user_level":-1,"id":0,"graph":"data/A2","agents":1}}
10-{"GameServer":{"pokemons":5,"is_logged_in":false,"moves":1823,"grade":0,"game_level":10,"max_user_level":-1,"id":0,"graph":"data/A2","agents":1}}
11-
12-{"GameServer":{"pokemons":1,"is_logged_in":false,"moves":1829,"grade":0,"game_level":12,"max_user_level":-1,"id":0,"graph":"data/A3","agents":1}}
13-
14-
15-{"GameServer":{"pokemons":4,"is_logged_in":false,"moves":3663,"grade":0,"game_level":15,"max_user_level":-1,"id":0,"graph":"data/A3","agents":1}}


