# SOLID-Principles-4-Interface-Segregation-Principle-ISP-
#Clients should not be forced to depend upon methods that they do not use.Interfaces belong to clients, not to hierarchies
from abc import ABC, abstractmethod
class Printer(ABC):
  @abstractmethod
  def print(self, document):
    pass
  @abstractmethod
  def fax(self, document):
    pass
  @abstractmethod
    def scan(self, document):
      pass
class OldPrinter(Printer):
  def print(self, document):
    print(f"Printing {document} in black and white...")
  def fax(self, document):
    raise NotImplementedError("Fax functionality not supported")
  def scan(self, document):
    raise NotImplementedError("Scan functionality not supported")
class ModernPrinter(Printer):
  def print(self, document):
    print(f"Printing {document} in color...")
  def fax(self, document):
    print(f"Faxing {document}...")
  def scan(self, document):
    print(f"Scanning {document}...")
#In this example, the base class, Printer, provides the interface that its subclassesmust implement. OldPrinter inherits from Printer and must implement the sameinterface. However, OldPrinter doesn’t use the .fax() and .scan() methodsbecause this type of printer doesn’t support these functionalities.
