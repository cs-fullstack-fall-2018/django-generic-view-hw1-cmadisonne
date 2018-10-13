# django-generic_view-hw1

Watch the video here about generic class views: https://docs.djangoproject.com/en/2.1/topics/class-based-views/.

How do you write a generic class ListView?

class PublishedBook(ListView):

  templatename = 'books/books_by_publisher.html/'
  
def get_queryset(self):
  
  self.publisher = get_object_or_404(Publisher, name=self.kwargs['publisher'])
  
  return Book.objects.filter(publisher=self.publisher)

