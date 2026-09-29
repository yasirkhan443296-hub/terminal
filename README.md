decision = self.router.route(query)

if decision.destination == "rag_agent":  
        return self.rag_agent.answer(query)  

    elif decision.destination == "research_agent":  
        return self.research_agent.research(query)  

    elif decision.destination == "sql_agent":  
        return self.sql_agent.query(query)  

    else:  
        raise ValueError(  
            f"Unknown agent: {decision.destination}"

expalin thus code
