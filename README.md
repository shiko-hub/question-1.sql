# question-1.sql
CREATE TABLE Members (
    MemberID INT AUTO_INCREMENT PRIMARY KEY,
    FullName VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE,
    JoinDate DATE NOT NULL
);

CREATE TABLE Books (
    BookID INT AUTO_INCREMENT PRIMARY KEY,
    Title VARCHAR(200) NOT NULL,
    Author VARCHAR(100),
    PublishedYear YEAR,
    ISBN VARCHAR(13) UNIQUE NOT NULL
);

CREATE TABLE BorrowingRecords (
    RecordID INT AUTO_INCREMENT PRIMARY KEY,
    MemberID INT,
    BookID INT,
    BorrowedDate DATE NOT NULL,
    ReturnDate DATE,
    FOREIGN KEY (MemberID) REFERENCES Members(MemberID),
    FOREIGN KEY (BookID) REFERENCES Books(BookID)
);

INSERT INTO Members (FullName, Email, JoinDate) VALUES
('John Doe', 'johndoe@example.com', '2025-04-20');

INSERT INTO Books (Title, Author, PublishedYear, ISBN) VALUES
('The Great Gatsby', 'F. Scott Fitzgerald', 1925, '1234567890123');
